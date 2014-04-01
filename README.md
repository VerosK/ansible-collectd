ansible-collectd
================

This is Ansible playbook for collectd. Feel free to use and abuse it.

Example installation
--------------------

Send data to collectd server
    ---
    - name: Install collectd
      hosts: all
      roles:
       - { role: collectd, tags: collectd,
           with_output_plugins: [ rrdtool ],

        }


Send data to collectd server
    ---
    - name: Install collectd and send data to collectd_server
      hosts: all
      roles:
       - { role: collectd, tags: collectd,
           with_interfaces: [eth0, lo],
           with_output_plugins: [ rrdtool, network  ],
           with_send_to: "collectd_server",
        }
