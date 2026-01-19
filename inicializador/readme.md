1. Criar o arquivo de serviço
Abra o terminal e crie um novo arquivo de configuração para o systemd:

Bash: sudo nano /etc/systemd/system/valheim.service

2. Configurar o conteúdo do serviço
Cole o conteúdo abaixo, ajustando os caminhos conforme a sua instalação:

```
[Unit]
Description=Valheim Dedicated Server
After=network.target

[Service]
Type=simple
# Substitua 'ubuntu' pelo seu usuário do sistema
User=ubuntu
# Coloque o caminho completo para a pasta onde está o script
WorkingDirectory=/home/ubuntu/valheim_server
# Coloque o caminho completo para o arquivo .sh
ExecStart=/bin/bash /home/ubuntu/valheim_server/my_server.sh
Restart=on-failure
RestartSec=10
KillSignal=SIGINT

[Install]
WantedBy=multi-user.target
```

Dica Importante: Certifique-se de que o seu arquivo my_server.sh tenha permissão de execução. Se não tiver, rode: chmod +x /home/ubuntu/valheim_server/my_server.sh.

3. Ativar e Iniciar o Serviço
Agora, você precisa avisar o sistema que um novo serviço foi criado e habilitá-lo para o boot:

Recarregar o systemd:

Bash: sudo systemctl daemon-reload

Habilitar a inicialização automática:

Bash: sudo systemctl enable valheim.service

Iniciar o servidor agora:

Bash: sudo systemctl start valheim.service

4. Comandos Úteis de Gerenciamento
Agora que o Valheim é um serviço do sistema, você pode controlá-lo facilmente:
Ver status (se está online ou se deu erro): sudo systemctl status valheim.service
Parar o servidor: sudo systemctl stop valheim.service

Reiniciar o servidor: sudo systemctl restart valheim.service

Ver os logs em tempo real: journalctl -u valheim.service -f
