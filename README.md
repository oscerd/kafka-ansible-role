Role for Kafka

An example of Kafka role use:

```yaml
---
- name: role kafka
  hosts: localhost
  remote_user: user
  
  roles:
    - role: camel-kafka-connector-ansible-role
      kafka_version: 2.8.1
      path_dir: /home/user/
      unarchive_dest_dir: /home/user/kafka/
      plugin_path_dir: /home/user/connectors/
      connectors:
        - "aws2-s3"
        - "aws2-sqs"
      start_kafka: true
```

## Role options

| Name                                 | Description                                                                         | Default
|--------------------------------------|-------------------------------------------------------------------------------------|-----------------------
| kafka_version                        | The version of Kafka to be used                                                     | 2.8.1
| scala_version                        | The version of Scala to be used while downloading Kafka                             | 2.12
| path_dir                             | The location of the Kafka tar.gz distribution                                       | /opt/
| unarchive_dest_dir                   | The location of the dir where to unarchive the Kafka tar.gz distribution            | /opt/kafka/
| plugin_path_dir                      | The plugin.path value to be set in connect standalone configurations                |
| connectors_version                   | The camel-kafka-connector connectors version                                        | 0.10.1
| connectors                           | A list of camel-kafka-connectors (eg. aws2-s3, aws2-sqs)                            |
| start_kafka                          | Automatically start kafka and zookeeper as daemons                                  | false
| wait_time_zookeeper                  | Wait for this time after starting zookeeper                                         | 10
| wait_time_kafka                      | Wait for this time after starting kafka                                             | 10
