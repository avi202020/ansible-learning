- Run: `vagrant up` to start all these three machines:
Networking:private_network
Master:192.168.4.2
Slave1:192.168.4.3
Slave2:192.168.4.4

- To SSH to one machine:
`ssh  -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no -i key/ansible_id_rsa vagrant@192.168.4.2`

- Run ad hoc ansible helloworld to test the setup is working:
`ansible all -a "/bin/echo hello" -u vagrant -i inventory.ini --private-key key/ansible_id_rsa`
