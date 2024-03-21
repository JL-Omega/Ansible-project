# Web Application Deployment Role

This Ansible role is designed to automate the deployment of a web application onto remote hosts. It performs the following tasks:

## Tasks

### 1. Ping Hosts
- **Description**: Ensures that the hosts are reachable and responsive.
- **Module Used**: ansible.builtin.ping

### 2. Copy Application Files
- **Description**: Copies the application files from the local machine to the specified directory on the remote host.
- **Module Used**: ansible.builtin.copy
- **Source**: app/
- **Destination**: /home/jean-luc/ansible

### 3. Template the Application Index Page
- **Description**: Templates the application index page using Jinja2 templates and deploys it to the remote host.
- **Module Used**: ansible.builtin.template
- **Source Template**: index.html.j2
- **Destination**: /home/jean-luc/ansible/index.html

### 4. Create Apache Container
- **Description**: Deploys an Apache container using Docker on the remote host to serve the web application.
- **Module Used**: community.docker.docker_container
- **Container Name**: apache
- **Image**: httpd
- **Restart Policy**: true
- **Exposed Ports**: 80
- **Volume Mapping**: /home/jean-luc/ansible:/usr/local/apache2/htdocs/

## Usage

To use this role, include it in your Ansible playbook and provide necessary variables such as hosts, paths, and container configurations as needed.

Example playbook snippet:

```yaml
- name: Deploy Web Application
  hosts: web_servers
  roles:
    - webapp

Replace web_servers with your target hosts.

## Author

This Ansible role was authored by ***JL Mpande*** and is licensed under [License] (if applicable). For contributions or issues, please visit [https://github.com/JL-Omega/Ansible-project.git].

## Disclaimer
This role is provided as-is, without any warranties or guarantees. Users are advised to review and customize it as per their specific requirements and environments.