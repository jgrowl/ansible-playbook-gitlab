# ansible-playbook-gitlab

Playbook for installing GitLab 5.4-stable on ubuntu 12.04.

GitLab is a truly awesome platform for doing development within a business, but setting it up manually is tiring and error-prone as it requires many steps that needs to be executed. This Ansible playbook aims to solve this problem by significantly reducing the amount of steps.

## Prerequisites
You need to have sudo installed on the server and Ansible on the client. 

The playbooks use the apt module, and for that reason they only work on Debian-based distributions. They are currently only tested on ubuntu server 12.04. Patches are welcome for extending support for other platforms. 

## Assumptions
You should probably have dns set up with a record that points to the box you would like to install gitlab to (gitlab.example.com) 
The box that you are installing gitlab to needs to be able to resolve the gitlab address you setup in order to connect to gitlab-shell (ping gitlab.example.com from the box)

## Installation

`git clone --recursive` 

or clone normally and:

`git submodule init && git submodule update`

Copy vars/main.template.yml into .ansible-playbook-gitlab/vars/main.yml or use submodule and update configuration to suit your desired configuration.

`mkdir -p .ansible-playbook-gitlab/vars/`

`cp vars/main.template.yml .ansible-playbook-gitlab/vars/main.yml`

Edit hosts file and add the ip of the machine you wish to install gitlab to.

Run the playbook 

`ansible-playbook -cssh -i /etc/ansible/playbooks/ansible-playbook-gitlab/hosts /etc/ansible/playbooks/ansible-playbook-gitlab/main.yml`

Now you should be able to log in with the following credentials:

username `admin@local.host`

password `5iveL!fe` 

## Credits
Originally forked from https://github.com/tingtun/ansible-playbook-gitlab and playbook template from https://github.com/conikeec/ansible-playbook-template

## License
Copyright © 2012 Tingtun

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
