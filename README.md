<h1>Автоматизация развёртывания платформы "Moodle" для дистанционного обучения</h1>

<p>
    <strong>Шаг 1.</strong> Создание playbook для запуска роли
</p>
<p><i>Пример:</i></p>

    ---
    - name: Deploy Moodle
    hosts: all 
    become: true 

    roles: 
        - ansible-role-moodle

<p>
    <strong>Шаг 2.</strong> Склонировать роль в дирректорию с playbook:
</p>

  <pre>git clone https://github.com/NewErr0r/ansible-role-moodle.git</pre>

<p>
    <strong>Шаг 3.</strong> Запустить скрипт инициализирующий необходимые переменные:
</p>
 
 <pre>./ansible-role-moodle/configure.variables</pre>
 <i>1. Задать пароль MariaDB для пользователя root</i><br>
 <i>2. Задать имя базы данных MariaDB для moodel</i><br>
 <i>3. Задать имя пользователя MariaDB для moodle </i><br>
 <i>4. Задать пароль для этого пользователя </i>
 
 <p>
    <strong>Шаг 4.</strong> Запустить playbook для развёртывания платформы Moodle:
</p>
  
  <pre>ansible-playbook -i inventory playbook.yaml</pre>
