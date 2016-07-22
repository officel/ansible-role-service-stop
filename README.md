Ansible Role: service stop
=========

[![Build Status](https://travis-ci.org/officel/ansible-role-service-stop.svg?branch=master)](https://travis-ci.org/officel/ansible-role-service-stop)

disable service. maybe unneeded services.

Requirements
------------

none.

Role Variables
--------------

default stop_services are...

    stop_services: 
      - auditd       # 監査システム。
      - lvm2-monitor # 論理ボリュームマネージャー。
      - mdmonitor    # ソフトウエアRAID監視デーモン。
      - netfs        # NFSクライアントデーモン。
      - nfs          # NFSサーバ。
      - nfslock      # NFSサーバのファイルロック機構。
      - iptables     # ファイアーウォール

Dependencies
------------

none.

Example Playbook
----------------

    - hosts: all
      roles:
         - officel.service-stop

         or

         - {role: officel.service-stop,
            stop_services: [ auditd , nfs ]
           }

One more thing
--------------

    $ chkconfig | grep on

License
-------

MIT / BSD

Author Information
------------------

This role was created by raki.
