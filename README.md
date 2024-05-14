# Project Title

This project uses Ansible to automate the deployment of a monitoring stack consisting of Prometheus, Grafana, and Node Exporter. 

## Project Structure

```
.
├── README.md
├── ansible.cfg
├── grafana_deploy.yml
├── inventory
├── node-exporter_deploy.yml
├── prometheus_deploy.yml
└── roles
    ├── grafana
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   ├── main.yml
    │   │   └── main.yml.backup
    │   ├── templates
    │   │   ├── dashboard.yml
    │   │   ├── datasource.yml
    │   │   └── node-exporter-full.json
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    ├── node_exporter
    │   ├── README.md
    │   ├── defaults
    │   │   └── main.yml
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   └── node_exporter.service
    │   ├── tests
    │   │   ├── inventory
    │   │   └── test.yml
    │   └── vars
    │       └── main.yml
    └── prometheus
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── tasks
        │   ├── install_prometheus.yml
        │   └── main.yml
        ├── templates
        │   └── prometheus.service
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
```

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Ansible
- SSH access to your servers

### Installing

1. Clone the repository to your local machine.
2. Update the `inventory` file with the IP addresses and SSH details of your servers.
3. Run the Ansible playbooks to deploy the monitoring stack.

```bash
ansible-playbook -l 'prometheus_srv' prometheus_deploy.yml
ansible-playbook -l 'grafana_srv' grafana_deploy.yml
ansible-playbook node-exporter_deploy.yml
```

## Deployment

This project can be deployed on any servers with SSH access.

## Built With

- [Ansible](https://www.ansible.com/) - Automation tool

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details