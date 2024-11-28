# Развертывание Drupal с помощью Ansible

1. Установлен Ansible на узле управления.
2. Были загружены необходимые роли с помощью команд:
   - ansible-galaxy install geerlingguy.nginx
   - ansible-galaxy install geerlingguy.postgresql
   - ansible-galaxy install geerlingguy.php
   - ansible-galaxy install geerlingguy.drupal
   - ansible-galaxy install geerlingguy.php-versions
   - ansible-galaxy install geerlingguy.php-pgsql
   - ansible-galaxy install geerlingguy.composer
4. Добавил в файл /atc/ansible/hosts строку 192.168.56.8   
5. Создаy файл инвентаризации `inventory` 192.168.56.8 ansible_user=user
6. Определите переменные в файле `vars/default.yml`.
7. Запуск playbook с помощью команды:
   ansible-playbook -i inventory.ini playbooks.yml -kK| tee ~/ansible-drupal/deployment.log 
8. Получен файл `deployment.log` для получения информации о выполнении сценария.
