**Overview**

This is an Ansible playbook for automating the provisioning of a server for
hacking on or running the [robcutmore.com](http://www.robcutmore.com) website.
The website is currently developed and deployed on Ubuntu.

**Getting Started**

Update Ansible hosts file (*/etc/ansible/hosts*) with target IP addresses:

    [production]
    Enter production server IP address here

Clone this repo to your local machine:

    git clone https://github.com/rcutmore/robcutmore.com-ansible.git
    cd ./robcutmore.com-ansible/

Replace variable placeholders (*[...]*'s):

    vi ./group_vars/all
    :%s/enter_db_engine_here/[Replace this with database engine]/g
    :%s/enter_db_host_here/[Replace this with database host]/g
    :%s/enter_db_name_here/[Replace this with database name]/g
    :%s/enter_db_password_here/[Replace this with database password]/g
    :%s/enter_db_port_here/[Replace this with database port]/g
    :%s/enter_db_user_here/[Replace this with database user]/g
    :x
    vi ./roles/django-project/vars/main.yml
    :%s/enter_django_debug_here/[Replace this with Django debug state (True or False)]/g
    :%s/enter_django_secret_key_here/[Replace this with Django secret key]/g
    :%s/enter_django_template_debug_here/[Replace this with Django template debug state (True or False)]/g
    :%s/enter_git_name_here/[Replace this with Git name]/g
    :%s/enter_git_email_here/[Replace this with Git email]/g
    :%s/enter_project_user_here/[Replace this with OS user]/g
    :x

Set up development server:

    sudo ansible-playbook ./development.yml

