# valheim-dedicated-server-ec2-aws
Como criar um servidor dedicado do valheim na aws

Primeiro passo é criar a instancia ec2 na aws seguindo esse tutorial

https://www.youtube.com/watch?v=ZkLAz8zrKjM

lembrar de  criar a sua credencial putty para acessar o console

como esse video é de 2023

IP: 18.229.156.60

Após conectar no console vc deve 

sudo apt update
sudo apt -y dist-upgrade
sudo apt-get -y install lib32gcc-s1
sudo apt-get -y install libsdl2-2.0-0
sudo apt-get install -y ca-certificates libpulse-dev libatomic1

mkdir SteamCMD && cd SteamCMD
curl -sqL "https://steamcdn-a.akamaihd.net/clien..." | tar zxvf -
/home/ubuntu/SteamCMD/steamcmd.sh +login anonymous +force_install_dir /home/ubuntu/Steam +app_update 896660 validate +exit
cd /home/ubuntu/Steam/
cp start_server.sh my_start_server.sh
screen -S scr
./my_start_server.sh



ou

sudo apt-get update
sudo add-apt-repository multiverse
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install -y steamcmd

steamcmd

steamcmd +force_install_dir /home/ubuntu/Steam +login anonymous +app_update 896660 validate +exit

Raiz da pasta: /home/ubuntu/Steam
https://steamcommunity.com/sharedfiles/filedetails/?id=2383801614

Pasta do mundo no linux
 cd /home/ubuntu/.config/unity3d/IronGate/Valheim


baixar mundo do drive

sudo apt install python3-pip -y
sudo apt install -y pipx
pipx ensurepath
pipx install gdown

gdown "https://drive.google.com/file/d/1MNaqh4RYhzQeICdW8LOzAw5aOj2CvqIG/view?usp=drive_link"
gdown "https://drive.google.com/file/d/1EKFL8jG-CkEgCHdvX3cKvh_vvNw2BZ9R/view?usp=drive_link"
gdown "https://drive.google.com/file/d/1T8-Rp-2HIVcR6i8nPqLYoKJbP4Mgy4ri/view?usp=drive_link"


