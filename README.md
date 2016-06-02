This is an Ansible playbook for automating the provisioning of a server for
hacking on or running the [robcutmore.com](http://www.robcutmore.com) website.
The website is currently developed and deployed on Ubuntu.

To get started clone this repo to your local machine:

    git clone https://github.com/rcutmore/robcutmore.com-ansible.git
    cd ./robcutmore.com-ansible/

Replace variable placeholders:

    vi ./group_vars/all
    :%s/enter_project_user_here/[Replace this with OS user]/g
    :x
    vi ./roles/django-project/vars/main.yml
    :%s/enter_git_name_here/[Replace this with Git name]/g
    :%s/enter_git_email_here/[Replace this with Git email]/g
    :x
    vi ./roles/postgresql/vars/main.yml
    :%s/enter_db_user_here/[Replace this with PostgreSQL user]/g
    :%s/enter_db_password_here/[Replace this with PostgreSQL password]/g
    :%s/enter_db_name_here/[Replace this with PostgreSQL database name]/g
    :x

To set up a development server:

    sudo ansible-playbook ./development.yml

