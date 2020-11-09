# Homework № 5 packer-base
 - Создан сервисный аккаунт на Yandex.Cloud;
 - Создан файл-шаблон Packer;
 - Средствами пакера собран образ Ubuntu;
 - Развернута ВМ из образа, развернуто и проверено приложение;
 - Параметризирван созданный шаблон, переменные определены в файле variables.json.

# Homework № 4 cloud-testapp
 - Установлен и настрое yc CLI;
 - Создан хост с помощью CLI;
 - На хосте установлены ruby, MongoDB;
 - Произведен деплой тестового приложенния.

testapp_IP = 84.201.134.222
testapp_port = 9292

 Команда CLI с использованием метаданных пользователя:
 yc compute instance create \
  --name reddit-app \
  --hostname reddit-app \
  --memory=4 \
  --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB \
  --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
  --metadata-from-file user-data=./startup_script.yaml \
  --metadata serial-port-enable=1 \

# Homework № 3 Cloud-bastion
  Подключение к someinternalhost в одну строку:
 ssh -i ~/.ssh/appuser -A -tt appuser@84.201.171.110 ssh -tt 10.128.0.17
  Для подключение по алиасу ssh someinternalhost требуется прописать в ~/.ssh/config следующие:
    Host bastion
     HostName 84.201.171.110
     Port 22
     User appuser
     IdentityFile /home/deriabin/.ssh/appuser
    Host someinternalhost
     HostName 10.128.0.17
     Port 22
     User appuser
     IdentityFile /home/deriabin/.ssh/appuser
     ProxyJump bastion

bastion_IP = 84.201.171.110
someinternalhost_IP = 10.128.0.17

# Homework № 2 Play-Travis
 - Добавлен хук  pre-commit;
 - Добавлен шаблон PULL_REQUEST_TEMPLATE;
 - Произведена интеграция Slack;
 - Репозитории подключены к тестам Travis CI.

# sanya-derya_infra
sanya-derya Infra repository
