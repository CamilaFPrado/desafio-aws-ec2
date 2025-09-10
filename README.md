# Desafio Prático: Gerenciamento de Instâncias EC2 na AWS

Este repositório documenta minha experiência e aprendizado no desafio de gerenciamento de instâncias EC2 na AWS, consolidando os conhecimentos adquiridos durante as aulas.

## 📋 Índice
- [Introdução](#introdução)
- [Conceitos Fundamentais](#conceitos-fundamentais)
- [Passo a Passo da Implementação](#passo-a-passo-da-implementação)
- [Anotações e Insights](#anotações-e-insights)
- [Melhores Práticas](#melhores-práticas)
- [Conclusão](#conclusão)
- [Estrutura do Repositório](#estrutura-do-repositório)

---

## Introdução

O Amazon EC2 (Elastic Compute Cloud) é um serviço fundamental da AWS que fornece capacidade computacional redimensionável na nuvem. Este desafio teve como objetivo praticar a criação, configuração e gerenciamento de instâncias EC2, consolidando os conhecimentos teóricos por meio da experiência prática.

---

## Conceitos Fundamentais

### Componentes Principais do EC2
- **Instâncias**: Máquinas virtuais executadas na AWS
- **AMIs (Amazon Machine Images)**: Modelos pré-configurados para instâncias
- **Tipos de Instância**: Diferentes combinações de CPU, memória, armazenamento e rede
- **Security Groups**: Firewalls virtuais que controlam o tráfego
- **Key Pairs**: Credenciais de segurança para acessar as instâncias
- **EBS (Elastic Block Store)**: Volumes de armazenamento persistente

### Modelos de Preços
- **On-Demand**: Pagamento por uso sem compromisso
- **Reserved Instances**: Desconto por compromisso de uso a longo prazo
- **Spot Instances**: Licitação por capacidade ociosa com economia significativa
- **Savings Plans**: Modelo de preço flexível com desconto por uso consistente

---

## Passo a Passo da Implementação

### 1. Configuração Inicial
- Criação de uma conta AWS (se necessário)
- Acesso ao console de gerenciamento AWS
- Navegação até o serviço EC2

### 2. Criação da Instância EC2
- Seleção da AMI apropriada (Amazon Linux 2)
- Escolha do tipo de instância (t2.micro - elegível para free tier)
- Configuração dos detalhes da instância
- Adição de armazenamento (volume EBS padrão)
- Configuração de Security Groups (permitindo SSH e HTTP)
- Criação e download do par de chaves

### 3. Conexão com a Instância
```bash
# Comando para conectar via SSH
ssh -i "chave.pem" ec2-user@ip-publico-instancia
```

### 4. Configuração e Personalização
- Atualização dos pacotes
- Instalação do servidor web (Apache)
- Configuração de página HTML simples
- Teste de acesso via navegador

### 5. Monitoramento e Gerenciamento
- Utilização do CloudWatch para monitoramento
- Configuração de alarmes simples
- Gerenciamento do estado da instância (iniciar, parar, reiniciar)

### 6. Limpeza e Encerramento
- Término da instância para evitar cobranças indesejadas

---

## Anotações e Insights

💡 **Aprendizados Importantes**

**Segurança é Prioritária:**
- Sempre usar pares de chaves em vez de senhas
- Configurar Security Groups com o princípio do menor privilégio
- Nunca expor portas desnecessárias para a internet

**Otimização de Custos:**
- Sempre desligar instâncias quando não estiver em uso
- Considerar instâncias Spot para cargas de trabalho tolerantes a falhas
- Utilizar tags para organização e controle de custos

**Resiliência e Alta Disponibilidade:**
- Distribuir instâncias em múltiplas zonas de disponibilidade
- Utilizar Elastic IP para endereços IP estáticos
- Considerar Auto Scaling Groups para carga variável

📊 **Dados Técnicos Relevantes**

| Parâmetro | Configuração | Observação |
|---|---|---|
| Tipo de Instância | t2.micro | Elegível para free tier |
| AMI | Amazon Linux 2 | Estável e bem suportada |
| Armazenamento | 8 GB GP2 | Suficiente para aplicações simples |
| Security Groups | SSH (22), HTTP (80) | Acesso mínimo necessário |

---

## Melhores Práticas

**Gerenciamento de Instâncias**
- Usar IAM Roles em vez de armazenar credenciais na instância
- Implementar sistemas de patch management para manter as instâncias atualizadas
- Utilizar User Data para automatizar configurações iniciais

**Monitoramento**
- Habilitar monitoramento detalhado no CloudWatch
- Configurar alarmes para métricas importantes (CPU, memória, disco)
- Utilizar AWS Systems Manager para gerenciamento centralizado

**Backup e Recuperação**
- Criar snapshots regulares dos volumes EBS
- Criar AMIs personalizadas para recuperação rápida
- Implementar estratégias de backup cross-region para disaster recovery

---

## Conclusão

Este desafio prático proporcionou uma compreensão sólida do serviço EC2 da AWS, desde a criação básica de instâncias até considerações avançadas de segurança, custo e alta disponibilidade. A documentação do processo não apenas consolidou o aprendizado, mas também criou um recurso valioso para referência futura.

A experiência com o EC2 demonstrou a flexibilidade e poder da computação em nuvem, permitindo que recursos de TI sejam provisionados e gerenciados de maneira ágil e econômica.

---

## Estrutura do Repositório

```text
/desafio-ec2-aws
│
├── /images
│   ├── console-ec2.png
│   ├── security-group.png
│   └── instancia-ativa.png
│
├── README.md
└── comandos-uteis.md
