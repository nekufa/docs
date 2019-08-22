# Как начать работать с {{ mmy-short-name }}<sup>®</sup>

Перед тем, как создать кластер баз данных:

1. Если у вас уже есть каталог в Яндекс.Облаке, откройте страницу этого каталога в консоли управления. Если каталога еще нет, создайте его:

    {% include [create-folder](../_includes/create-folder.md) %}

1. Создайте виртуальную машину (на основе [Linux](../compute/quickstart/quick-create-linux.md) или [Windows](../compute/quickstart/quick-create-windows.md)), с которой вы будете обращаться к кластеру БД. Если вы планируете подключаться к базе данных извне Облака, запросите внешние IP-адреса для хостов при создании кластера.

Ниже приведены инструкции, следуя которым можно быстро создать кластер и проверить подключение к нему.

1. В консоли управления выберите каталог, в котором нужно создать кластер БД.
1. Выберите сервис **{{ mmy-name }}**.
1. Нажмите кнопку **Создать кластер** и выберите нужную СУБД.
1. Задайте параметры кластера и нажмите кнопку **Создать кластер**. Процесс подробно рассмотрен в разделе [{#T}](operations/cluster-create.md).
1. Когда кластер будет готов к работе, его статус на панели {{ mmy-short-name }} сменится на **RUNNING**.
1. Чтобы подключиться к серверу БД, необходим SSL-сертификат. Подготовить все нужные аутентификационные данные можно, например, так:

    ```bash
    $ mkdir ~/.mysql
    $ wget "https://{{ s3-storage-host }}{{ pem-path }}" -O ~/.mysql/root.crt
    $ chmod 0600 ~/.mysql/root.crt
    ```

1. К БД можно подключиться командой `mysql` (подробнее — в разделе [{#T}](operations/connect.md)):
    ```
    $ mysql --host=<адрес хоста>
            --port=3306
            --ssl-ca=~/.mysql/root.crt
            --ssl-mode=REQUIRED
            --user=<имя пользователя базы данных>
            --password <имя базы данных>
    ```