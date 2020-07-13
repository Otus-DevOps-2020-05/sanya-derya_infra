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
