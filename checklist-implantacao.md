# Checklist de Implantação EC2

## Pré-Implantação
- [ ] Definir requisitos de hardware (tipo de instância)
- [ ] Escolher AMI apropriada
- [ ] Selecionar região e zona de disponibilidade
- [ ] Planejar estratégia de rede (VPC, sub-rede)
- [ ] Preparar par de chaves SSH

## Durante a Implantação
- [ ] Configurar Security Groups adequadamente
- [ ] Selecionar tipo de instância correto
- [ ] Configurar storage (tamanho e tipo do EBS)
- [ ] Adicionar tags para organização
- [ ] Revisar configurações antes de lançar

## Pós-Implantação
- [ ] Testar conexão SSH
- [ ] Atualizar sistema operacional
- [ ] Instalar software necessário
- [ ] Configurar monitoramento
- [ ] Implementar backups
- [ ] Documentar configurações

## Segurança
- [ ] Configurar Security Groups com mínimo de portas abertas
- [ ] Usar pares de chaves em vez de senhas
- [ ] Atualizar regularmente o sistema
- [ ] Configurar IAM roles apropriadas
- [ ] Implementar logging e monitoramento

## Otimização de Custos
- [ ] Escolher tipo de instância adequado à carga de trabalho
- [ ] Considerar instâncias Spot para workloads flexíveis
- [ ] Configurar alarmas de billing
- [ ] Usar tags para tracking de custos
- [ ] Planejar schedule de parada para instâncias de desenvolvimento

## Monitoramento
- [ ] Habilitar monitoramento detalhado no CloudWatch
- [ ] Configurar alarmas para métricas críticas
- [ ] Implementar logging centralizado
- [ ] Estabelecer processos de resposta a incidentes

## Backup e Recovery
- [ ] Configurar snapshots automáticos do EBS
- [ ] Criar AMIs regularmente
- [ ] Testar processo de restore
- [ ] Documentar procedimentos de recovery
