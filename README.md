# repo-ops-playbook 🤖
As a developers, we're always creating local or remote repositories on [Github]
(https://www.github.com) or another platform to code our ideas.

I decided it was time to automate this operation, to become faster, efficient
and focus of what matters. 

With all that said, I introduce two Ansible playbooks that will take care of:

1. Creating a remote development repository on Github.
2. Clone this repository to your local machine.
3. Create the development branch locally and remotely.
4. Provision the repository with a default README.md and MIT license files.
5. Destroy all data related with the repository (if you have to).

## Prerequisites

To run these playbooks you will need:

* [A Github account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).
* The [Github CLI](https://cli.github.com) (2.6.0+) installed.
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) (2.12.2+) installed. 

## Installation

1. Download a copy of this repository on the device Ansible is installed:

```bash
git clone https://github.com/etoromol/repo-ops-playbook.git
```

2. Change project directory:
```bash
cd repo-ops-playbook
```

## Configuration

3. Make sure to have the IP Address of the device (where the repository will be
deployed) specified within the hosts key in the playbooks. Because I'm using my
computer, the current hosts key looks like:

 ```yml                                                                         
 hosts: localhost                                                            
``` 

## Deployment

4. To run the playbooks and deploy the repositories, use the command below:

```bash
 ansible-playbook deploy_repo.yml
```

5. To destroy the already created repository, use the destroy playbook:
```bash
 ansible-playbook destroy_repo.yml
```

## License

Copyright (c) 2022 Eduardo Toro.

Licensed under the [MIT](LICENSE) license.
