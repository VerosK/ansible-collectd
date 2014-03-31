ansible-collectd
================

This is Ansible playbook for collectd. Feel free to use and abuse it.

Example installation
--------------------

    ---
    - name: Install collectd and send data to collectd_server
      hosts: all
      roles:
       - { role: collectd, tags: collectd,
           with_interfaces: [eth0, lo],
           with_output_plugins: [ rrdtool, network  ],
           with_send_to: "collectd_server",
        }
