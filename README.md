Role Variables
--------------
Set prometheus_node_exporter_version: <> in defaults/main.yml

See defaults/main.yml. This role supports all collectors, just list the collectors using the prometheus_node_exporter_enabled_collectors variable.

Example Playbook
----------------

    - name: The Prometheus Node Exporter role
      hosts: node-exporter
      become: yes
      become_method: sudo

      vars:
        prometheus_node_exporter_enabled_collectors:
          - logind
        prometheus_node_exporter_disabled_collectors:
          - netstat

      roles:
        - ansible-role-prometheus-node-exporter

      tags:
        - node-exporter
