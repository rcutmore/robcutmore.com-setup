**Overview**

This is an Ansible playbook for automating the provisioning of a server for
hacking on or running the [robcutmore.com](http://www.robcutmore.com) website.
The website is currently developed and deployed on Ubuntu.

**Getting Started**

Update Ansible hosts file (*/etc/ansible/hosts*) with target IP addresses:

    [production]
    Enter production server IP address here
    
    [development]
    127.0.0.1

Clone this repo to your local machine:

    git clone https://github.com/rcutmore/robcutmore.com-ansible.git
    cd ./robcutmore.com-ansible/

Replace variable placeholders:

    vi ./roles/django-project/vars/main.yml
    :%s/enter_git_name_here/[Replace this with Git name]/g
    :%s/enter_git_email_here/[Replace this with Git email]/g
    :%s/enter_project_user_here/[Replace this with OS user]/g
    :x
    vi ./roles/postgresql/vars/main.yml
    :%s/enter_db_user_here/[Replace this with PostgreSQL user]/g
    :%s/enter_db_password_here/[Replace this with PostgreSQL password]/g
    :%s/enter_db_name_here/[Replace this with PostgreSQL database name]/g
    :x

Set up development server:

    sudo ansible-playbook ./development.yml

