# Automated Web Server Configuration using Ansible

## Files
- `inventory.ini`: identifies the target host. This demo uses localhost and Ansible's local connection.
- `setup_webserver.yml`: installs Nginx, ensures the service is running/enabled, and deploys the homepage.
- `index.html`: sample webpage copied to the web root.
- `run_instructions.txt`: commands and validation checklist.

## Important
This is a configuration example prepared for the assignment. It has not been executed on your laptop. Do not claim successful execution or attach invented screenshots. Run it in a supported Linux environment and capture your actual results before submission.

## Prerequisites
- Ubuntu/Debian-based Linux environment
- Python 3
- Ansible installed
- Internet access to install Nginx packages
- sudo privileges

## Run
From this directory:
    ansible --version
    ansible-inventory -i inventory.ini --list
    ansible-playbook -i inventory.ini setup_webserver.yml --ask-become-pass

If your Linux user can use sudo without a password, you may omit `--ask-become-pass`.
After success, open http://localhost in a browser.
