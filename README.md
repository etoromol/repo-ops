# repo-ops 🤖
As a developer, I'm always creating local or remote repositories to code my 
ideas. I decided it was time to automate this operation, to become faster,
efficient and focus on what really matters. 

With all that said, I introduce two Ansible playbooks that will take care of:

1. Creating a development repository on [Github](https://www.github.com).
2. Clone this repository to your local machine.
3. Create the development branch locally and remotely.
4. Provision the repository with a README.md file and MIT license.
5. Destroy all data related with the repository (if you have to).

## Prerequisites

To run these playbooks you will need:

* [A Github account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).
* [Github CLI](https://cli.github.com) (2.6.0+) installed.
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) (2.12.2+) installed. 

## Installation

1. Download a copy of this repository onto your Ansible device:

```bash
git clone https://github.com/etoromol/repo-ops.git
```

2. Change to the project directory:
```bash
cd repo-ops
```

## Configuration

3. Make sure to have the IP Address of the device (where the local repository 
will be deployed) specified within the hosts key in the playbooks. Because I'm 
using my own computer as the target, the current hosts key is localhost:

 ```yml                                                                         
 hosts: localhost                                                            
``` 

## Deployment

4. To run the playbooks i.e. deploy a repository, use the command below:

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
