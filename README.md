# d3-assessment

Clone this repo:

```$ git clone https://github.com/orezi/d3-assessment.git```

**Using Vagrant**

```$ cd d3-assessment```

```$ vagrant up```

- Put in appropriate IP addresses and path to ssh key of all 6 servers in ```inventory/hosts```

- Jump to Step 1

OR

**Using cloud provided servers**


**Requirements**

- IP addresses of 6 ubuntu 14.04 servers

- Put in appropriate IP addresses and path to ssh key of all 6 servers in ```inventory/hosts```


**Step 1:**

Sets up mysql on 1 master and 2 slave nodes

See variables in ```inventory/vars/all.yml``` and ```inventory/vars/slaves.yml```

- Set IP addresses for 2 wordpress servers (as defined in inventory/hosts) to allow connections on port 3306 and mysql replication master IP for replication

- Set IP address of mysql replication master (as defined in inventory/hosts)

**Run**

```ansible-playbook -i inventory/hosts master.yml```

AND

```ansible-playbook -i inventory/hosts slaves.yml```


**Step 2:**

Installs and sets up wordpress

- Set ```wp_db_host``` variable in ```roles/wordpress/defaults/main.yml``` to same as ```master``` in ```inventory/hosts```

**Run**

```ansible-playbook -i inventory/hosts wordpress.yml```


**Step 3:**

Sets up loadbalancer using haproxy

See variables in ```roles/haproxy/defaults/main.yml```

- Set IP addresses for 2 wordpress servers (as defined in inventory/hosts) to configure haproxy server to send traffic to

**Run**

```ansible-playbook -i inventory/hosts haproxy.yml```

**Results**

- Visit IP of haproxy server to complete wordpress installation

