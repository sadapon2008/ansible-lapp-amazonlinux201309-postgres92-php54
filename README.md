Ansible Playbook for CakePHP development on LAPP (Amazon Linux 2013.09 + PostgreSQL 9.2 + PHP 5.4)
-------------------------------------------

This playbook requires Ansible 1.4

    TARGET_HOST=x.x.x.x
    MAIN_USERNAME=username
    MAIN_PASSWORD=password
    DOCROOT=/var/www/html/docroot
    DBROOT=/var/lib/pgsql9
    CAKE_ENV_MODE=development
    env ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i <(echo ${TARGET_HOST}) -u ec2-user --private-key=~/.ssh/xxx.pem site.yml \
      --extra-vars "main_username=${MAIN_USERNAME} main_password=`openssl passwd -salt salty -1 ${MAIN_PASSWORD}` docroot=${DOCROOT} dbroot=${DBROOT} cake_env_mode=${CAKE_ENV_MODE}"
