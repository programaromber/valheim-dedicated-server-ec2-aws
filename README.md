# valheim-dedicated-server-ec2-aws
Como criar um servidor dedicado do valheim na aws

## AWS EC2
Primeiro passo é criar a instancia ec2 na aws seguindo esse tutorial:
- https://www.youtube.com/watch?v=ZkLAz8zrKjM
- Lembrar de  criar a sua credencial putty para acessar o console

# Configuração da máquina Ubuntu
Comandos:
```
sudo apt update
sudo apt -y dist-upgrade
sudo apt-get -y install lib32gcc-s1
sudo apt-get -y install libsdl2-2.0-0
sudo apt-get install -y ca-certificates libpulse-dev libatomic1
sudo add-apt-repository multiverse
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install -y steamcmd
cd /home/ubuntu/Steam/
steamcmd +force_install_dir /home/ubuntu/Steam +login anonymous +app_update 896660 validate +exit
- /home/ubuntu/Steam/steamcmd.sh +login anonymous +force_install_dir /home/ubuntu/Steam +app_update 896660 validate +exit
cp start_server.sh my_start_server.sh
screen -S scr
vim my_start_server.sh
- editar o nome do server e senha
./my_start_server.sh
```

Pasta do mundo no linux
 cd /home/ubuntu/.config/unity3d/IronGate/Valheim


# Backup
Comandos:
```
cd /home/ubuntu/.config/unity3d/IronGate/Valheim/worlds_local
git add .
git commit -m "backup"
git push -u origin main
```
login do github
- username
- senha token classico




