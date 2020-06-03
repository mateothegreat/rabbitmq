# rabbitmq ansible role

This role will install the latest version of rabbitmq
for centos 7.

## Variables

```yaml
rabbitmq:
  no_log: "true"
  users:
    - username: "test"
      password: "test"
  plugins:
    - "rabbitmq_consistent_hash_exchange"
    - "rabbitmq_management"
    - "rabbitmq_prometheus"
    - "rabbitmq_shovel"
    - "rabbitmq_shovel_management"
```

## Example Usage

Add the following to a file like `playbook.yaml`:

```yaml
- hosts: monitoring
  roles:
    - role: "mateothegreat.erlang"
    - role: "mateothegreat.rabbitmq"
      vars:
        rabbitmq:
          no_log: "true"
          users:
            - username: "test"
              password: "test"
          plugins:
            - "rabbitmq_consistent_hash_exchange"
            - "rabbitmq_management"
            - "rabbitmq_prometheus"
            - "rabbitmq_shovel"
            - "rabbitmq_shovel_management"
```

Run with `ansible-playbook -i <your inventory file> playbook.yaml`.

# Contact
Contact me at https://matthewdavis.io.
