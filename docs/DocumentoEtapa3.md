## Etapa 3: Gerência e Monitoração de Ambientes de Redes

A etapa 3 teve como foco a **configuração do sistema de monitoramento Zabbix**, tanto em ambiente local (VirtualBox) quanto em ambiente em nuvem (AWS), utilizando o protocolo **SNMP** para coletar dados de performance e disponibilidade dos dispositivos.

---

### 🖥️ Zabbix Appliance no VirtualBox

#### 1. Importação da Imagem
- A imagem do Zabbix Appliance foi importada para o Oracle VirtualBox.
- A máquina virtual foi inicializada com as configurações padrão.

#### 2. Configuração da Rede
- A VM foi configurada em modo **Bridge** ou **Rede Interna**, conforme o cenário de testes.
- Foi atribuído IP estático para garantir conectividade com a máquina host.

#### 3. Teste de Conectividade
- Ping da máquina host para a VM e vice-versa.
- Verificação via navegador do painel do Zabbix Appliance (porta 80).

#### 4. Configuração do Agente SNMP
- O serviço SNMP foi habilitado no host a ser monitorado.
- Parâmetros configurados: comunidade pública, localização e permissões de leitura.

#### 5. Adição do Host no Zabbix
- Inserção manual do endereço IP do host.
- Configuração do tipo de monitoramento via SNMP.
- Aplicação de templates predefinidos.

#### 6. Visualização de Gráficos
- Gráficos com consumo de CPU, memória, tráfego de rede e disponibilidade de serviços foram disponibilizados.

---

### ☁️ Zabbix Appliance na AWS

#### 1. Criação do Host
- Instância do Zabbix Appliance foi criada na VPC da AWS.

#### 2. Regras de Entrada – Segurança
- **SNMP (porta 161)**: habilitada no Security Group para comunicação com os dispositivos.
- **ICMP (ping)**: permitido para verificação de disponibilidade da instância.

#### 3. Configuração do SNMP na Instância Monitorada
- O protocolo SNMP foi configurado dentro da instância Windows Server 2016 na AWS.
- Regras de firewall foram ajustadas.

#### 4. Habilitação no Windows Server Cloud
- Serviços e funcionalidades ativados para permitir gerenciamento remoto.

#### 5. Coleta e Visualização de Dados
- Zabbix mostrou em tempo real as métricas do sistema Windows.
- Itens como uptime, utilização de disco, memória e rede foram monitorados.

#### 6. Mapa da Rede (Network Map)
- Criado um mapa com ícones representando a topologia da rede.
- Elementos conectados com status de cor e indicadores visuais (verde, amarelo, vermelho).

#### 7. Visão Global
- Painel principal do Zabbix com alertas ativos, disponibilidade geral e status de hosts.

---

### 🛠️ Considerações Finais

O uso do **Zabbix** permite:
- Monitoramento pró-ativo de falhas.
- Geração de alertas automáticos.
- Histórico de métricas para análise de capacidade.
- Integração com ambientes locais e em nuvem.

A configuração de **SNMP** foi essencial para conectar dispositivos diversos, consolidando o sistema de monitoração da infraestrutura da empresa de telemarketing.
