# Post checks automation 

## 1. Approach Followed

- **Automated Deployment:**
  - Ansible playbook automates deployment of the Spring Boot application.
  - Ensures any previous process using port 8083 is killed before deployment.
  - Application is always started as the intended user (`jagansai`), not as root.
  - All file and directory operations requiring root privileges use `become: yes`.

- **Post-Deployment Checks:**
  - Post-checks are defined in a YAML file (`commands_with_expected.yml`) with commands and their expected outputs.
  - Each command is executed, output is compared to the expected value, and results are collected.
  - An HTML report is generated summarizing the results, with pass/fail highlighting.

## 2. Ansible Command

Run the playbook with sudo password prompt:

```bash
ansible-playbook -i hosts deploy_compiler_backend.yml 
```

## 3. Post-Check Report


![Post Check Report Screenshot](resource/post_checks.jpeg)
