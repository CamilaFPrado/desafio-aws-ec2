# Comandos Úteis para Gerenciamento de Instâncias EC2

---

## Conexão SSH
```bash
# Conectar à instância
ssh -i "chave.pem" ec2-user@IP_PUBLICO

# Conectar com verificação de host estrita desabilitada (apenas para testes)
ssh -o StrictHostKeyChecking=no -i "chave.pem" ec2-user@IP_PUBLICO

# Conectar em modo verbose para debug
ssh -v -i "chave.pem" ec2-user@IP_PUBLICO
```

## Gerenciamento de Arquivos de Chave
```bash
# Alterar permissões da chave (obrigatório)
chmod 400 chave.pem

# Converter formato de chave (se necessário)
ssh-keygen -p -f chave.pem -m pem
```

## Comandos no Linux (Amazon Linux 2)
```bash
# Atualizar sistema
sudo yum update -y

# Instalar Apache
sudo yum install httpd -y

# Gerenciar serviço Apache
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd

# Verificar logs do Apache
sudo tail -f /var/log/httpd/access_log
sudo tail -f /var/log/httpd/error_log

# Instalar ferramentas adicionais
sudo yum install stress -y # Teste de carga de CPU
sudo yum install htop -y   # Monitoramento avançado
```

## AWS CLI (se instalado na instância)
```bash
# Ver informações da instância
aws ec2 describe-instances --instance-ids i-1234567890abcdef0

# Ver status da instância
aws ec2 describe-instance-status --instance-ids i-1234567890abcdef0

# Listar todas as instâncias
aws ec2 describe-instances

# Parar instância
aws ec2 stop-instances --instance-ids i-1234567890abcdef0

# Iniciar instância
aws ec2 start-instances --instance-ids i-1234567890abcdef0
```

## Monitoramento e Debug
```bash
# Ver uso de CPU
top
htop

# Ver uso de memória
free -h

# Ver uso de disco
df -h

# Ver processos em execução
ps aux

# Testar conectividade
ping google.com
curl ifconfig.me # Ver IP público
```

## Transferência de Arquivos
```bash
# SCP - Copiar arquivo para a instância
scp -i "chave.pem" arquivo.local ec2-user@IP_PUBLICO:/caminho/remoto/

# SCP - Copiar arquivo da instância
scp -i "chave.pem" ec2-user@IP_PUBLICO:/caminho/remoto/arquivo arquivo.local

# RSYNC - Sincronizar diretórios
rsync -avz -e "ssh -i chave.pem" diretorio/local/ ec2-user@IP_PUBLICO:/caminho/remoto/
```

## Segurança
```bash
# Verificar portas abertas
sudo netstat -tulpn

# Verificar conexões ativas
sudo ss -tunap

# Verificar regras de firewall
sudo iptables -L -n
```

## Script de User Data (para inicialização automática)
```bash
#!/bin/bash

# Atualizar sistema
yum update -y

# Instalar Apache
yum install httpd -y

# Iniciar Apache
systemctl start httpd
systemctl enable httpd

# Criar página inicial
echo "<html><body><h1>Instância configurada automaticamente!</h1></body></html>" > /var/www/html/index.html
```

