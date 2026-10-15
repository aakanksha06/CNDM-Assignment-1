# DevOps Lifecycle and Automated Web Server Configuration Using Ansible

 1. Project Overview

This project demonstrates the use of **DevOps practices and Ansible configuration management** to automate the setup of a basic web server.

The project uses Ansible to install and configure Nginx, ensure that the service is enabled and running, and deploy a custom HTML webpage. It also describes the major stages of the DevOps lifecycle: development, testing, deployment, and monitoring.

 2. Objectives

- Understand the DevOps lifecycle and workflow.
- Identify the development, testing, deployment, and monitoring stages.
- Prepare an Ansible inventory to define the target host.
- Create an Ansible playbook for automated web server configuration.
- Understand how automation improves consistency and reduces manual configuration effort.

 3. Technologies Used

- **Ansible** — Configuration management and automation.
- **Nginx** — Web server.
- **YAML** — Ansible playbook format.
- **HTML** — Sample webpage.
- **Git and GitHub** — Version control and project hosting.
- **Ubuntu/Linux** — Intended execution environment.

 4. Project Structure

```text
CNAD-IA-1/
├── CNDM_Assignment1_Report.pdf
├── Development_Testing_Deployment_Monitoring.docx
├── README.md
└── Ansible Files/
    ├── README.md
    ├── inventory.ini
    ├── setup_webserver.yml
    ├── index.html
    └── run_instructions.txt
```

 5. DevOps Lifecycle

The project follows these stages:

1. **Development:** Prepare the inventory, Ansible playbook, and HTML webpage.
2. **Testing:** Validate the inventory and playbook syntax, then check the service and webpage after execution.
3. **Deployment:** Use Ansible to install Nginx and deploy the webpage.
4. **Monitoring:** Check service availability, HTTP responses, and server logs.

 6. Ansible Configuration

The inventory file, `inventory.ini`, defines the target host. The current example uses a local connection to `localhost`.

The playbook, `setup_webserver.yml`, is designed to:

- Install Nginx using the APT package manager.
- Ensure that Nginx is started and enabled at system startup.
- Deploy `index.html` to `/var/www/html/index.html`.

The HTML file contains the sample webpage intended to be served by Nginx.

 7. Execution Instructions

Run the following commands in a supported Ubuntu/Linux environment with Ansible installed.

Navigate to the directory containing the Ansible files:

```bash
cd "Ansible Files"
```

Check the Ansible installation:

```bash
ansible --version
```

Validate the inventory:

```bash
ansible-inventory -i inventory.ini --list
```

Check the playbook syntax:

```bash
ansible-playbook -i inventory.ini setup_webserver.yml --syntax-check
```

Execute the playbook:

```bash
ansible-playbook -i inventory.ini setup_webserver.yml
```

After successful execution, check the Nginx service:

```bash
systemctl status nginx
```

Open the following address in a browser to check the deployed webpage:

```text
http://localhost
```

**Prerequisites:** The execution account must have appropriate administrative privileges. The playbook uses privilege escalation and APT, so the example is intended for a suitable Debian/Ubuntu-based environment.

 8. Testing and Monitoring Plan

The planned validation activities include:

- Checking the Ansible installation and inventory.
- Validating the playbook syntax.
- Reviewing the playbook execution output.
- Checking whether Nginx is active.
- Verifying the webpage in a browser.
- Inspecting Nginx service and error logs.

These checks are intended to validate the configuration after execution.

 9. Implementation Status

The project documentation and Ansible configuration files have been prepared. However, **the playbook has not yet been executed**, because the local WSL/Ubuntu environment could not be initialized successfully.

Therefore, successful deployment, service status, and webpage accessibility have not been verified. The execution instructions and test cases describe the planned procedure and expected outcomes, not confirmed results.

 10. Conclusion

This project presents a practical example of how Ansible can support the DevOps lifecycle by automating web server configuration. It demonstrates the intended roles of development, testing, deployment, and monitoring, and provides configuration files that can be used for practical validation in a suitable Linux environment.

11. References

- Ansible Documentation: https://docs.ansible.com/
- Nginx Documentation: https://nginx.org/en/docs/
- GitHub Documentation: https://docs.github.com/
