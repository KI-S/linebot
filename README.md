# linebot

## init

因為使用colab為執行環境，因此執行前需要先下載套建

```python
!pip install django
!pip install line-bot-sdk
!pip install beautifulsoup4
!pip install requests
!pip install transitions
```


接著因為要建ngrok到雲端方便執行，所以掛階雲端硬碟，並建立ngrok相關環境

```python
from google.colab import drive
drive.mount('/content/drive', force_remount=True)

!mkdir -p /drive
#umount /drive
!mount --bind /content/drive/My\ Drive /drive
!mkdir -p /drive/ngrok-ssh
!mkdir -p ~/.ssh

!mkdir -p /drive/ngrok-ssh
%cd /drive/ngrok-ssh
!wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip -O ngrok-stable-linux-amd64.zip
!unzip -u ngrok-stable-linux-amd64.zip
!cp /drive/ngrok-ssh/ngrok /ngrok
!chmod +x /ngrok
```

因為colab是使用雲端環境執行，所以使用flask_ngrok中的run_with_ngrok(app)來執行app

```python
!pip install flask_ngrok
```

## fsm

![image](https://github.com/KI-S/linebot/blob/main/fsm.png)
