sysinit-ansible-role
=========

Ansible role to system initialization on CentOS7

主要功能批量初始化服务器配置：

* 更新os和epel yum源
* 安装必备工具
* 配置时间同步
* 安全设置
  * 关闭selinux，firewalld，安装iptables-service
  * 关闭无用的service
  * 禁止ssh 密码认证登录，禁止root直接登录
* 内核参数优化

Requirements
------------

* CentOS/RHEL 7

Role Variables
--------------

* `pkgs:` 需要安装的安装包列表
* `ntp_servers:`需要同步的时间服务器列表
* `local_network:`允许同步时间的网段


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: servers
  remote_user: root
  gather_facts: false
  roles:
    - role: clay_wangzhi.sysinit
```

License
-------

BSD