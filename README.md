Role for Kafka

An example of Kafka role use:

```yaml
---
- name: role kafka
  hosts: localhost
  remote_user: user
  
  roles:
    - role: camel-kafka-connector-ansible-role
      kafka_version: 2.7.0
      path_dir: /home/user/
      unzip_dest_dir: /home/user/kafka/
