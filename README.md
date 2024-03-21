# Web Application Deployment

This repository contains an Ansible playbook for deploying a web application onto development (dev) servers. The playbook automates the deployment process by copying application files, templating the application index page, and creating an Apache container for hosting the web application.

## Prerequisites

Before running the playbook, ensure the following prerequisites are met:
- Ansible is installed on the local machine.
- Access to development servers configured in the inventory file.
- Docker installed on the target servers.

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/JL-Omega/Ansible-project.git
```

2. Navigate to the repository directory:

```bash
cd Ansible-project
```
3. Edit the `hosts.yml` file to include your server configurations.

4. Customize the `group_vars` files (`dev.yml` and `prod.yml`) with appropriate credentials and configurations for your environment.

5. Run the Ansible playbook:

```bash
ansible-playbook playbook.yml
```
## Playbook Structure

- `***playbook.yml:***` Main Ansible playbook file containing tasks for deploying the web application.
- `***roles/webapp/tasks/main.yml:***` Contains the tasks executed during the deployment process.
- `***group_vars/dev.yml and group_vars/prod.yml:***` Variables specific to development and production environments, including credentials and configurations.
- `***ansible.cfg:***` Ansible configuration file to specify settings like host key checking and inventory file location.

## Description of Tasks

1. ***Ping hosts:*** Tests connectivity to the target hosts.
2. ***Copy application files to the host:*** Copies application files from the local machine to the target server.
3. ***Template the application index page:*** Templates the index.html file using Jinja2 templating.
4. ***Create Apache container:*** Deploys an Apache container using Docker, exposing port 80 and mounting the application files as volumes.

## Configuration

### Development Environment (dev):

- Hostname: `fedora`
- IP Address: `Hidden`
- Ansible User: `jean-luc`
- Password: `Hidden`

### Production Environment (prod):

- Hostname: `debian`
- IP Address: `Hidden`
- Ansible User: `cheche`
- Password: `Hidden`


## Additional Notes

- Ensure Docker is installed on the target servers for container deployment.
- Modify the playbook and configurations as needed for your specific application and environment.

Feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/jean-luc-mpande-75981a23b/) for any further assistance or inquiries. Happy deploying!
