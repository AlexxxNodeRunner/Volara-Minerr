# Гайд на майнер Volara
 ![Gac4ky3WsAAZtPo](https://github.com/user-attachments/assets/c2479221-422f-4010-a4d6-fa184cae19c3)

**Устанавливаем Docker и обновляем пакеты на сервере**

```sudo apt update -y && sudo apt upgrade -y```

```for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done```

```sudo apt-get update```

```sudo apt-get install ca-certificates curl gnupg```

```sudo install -m 0755 -d /etc/apt/keyrings```

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg```

```sudo chmod a+r /etc/apt/keyrings/docker.gpg```

``echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null``

```sudo apt update -y && sudo apt upgrade -y```

```sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin```

```sudo chmod +x /usr/local/bin/docker-compose```

**Проверяем версию Docker**

```docker --version```

**Начинаем майнить**

```screen -S volara```

**Вместо PVKEY вставляем приватный ключ от EVM кошелька**

```docker pull volara/miner```

```export VANA_PRIVATE_KEY=PVKEY```

```docker run -it -e VANA_PRIVATE_KEY=${VANA_PRIVATE_KEY} volara/miner```

**После этого, скопируйте ссылку, которую вам выдали, откройте ее в браузе, зарегистрируйтесь. После этого выдадут Volara Auth Code. Вставьте его в терминал.**
<img width="1132" alt="Снимок экрана 2024-10-24 в 19 10 31" src="https://github.com/user-attachments/assets/75560f88-1a72-41ed-ba1d-0124a07db5f7">


**Далее, заполните следующие данные (никнейм в твиттере + пароль. Лучше отключить 2FA и использовать не основной аккаунт**

**После этого, майнинг начнется. Для выходов из логов нажмите Ctrl + A + D**
