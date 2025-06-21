## Etapa 3: Gerência e Monitoração de Ambientes de Redes

A etapa 3 teve como foco a **configuração do sistema de monitoramento Zabbix**, tanto em ambiente local (VirtualBox) quanto em ambiente em nuvem (AWS), utilizando o protocolo **SNMP** para coletar dados de performance e disponibilidade dos dispositivos.

---

### 🖥️ Zabbix Appliance no VirtualBox

#### 1. Importação da Imagem
- A imagem do Zabbix Appliance foi importada para o Oracle VirtualBox.
- A máquina virtual foi inicializada com as configurações padrão.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Importa%C3%A7%C3%A3o%20da%20imagem%20Zabbix.png)

#### 2. Configuração da Rede
- A VM foi configurada em modo **Bridge** ou **Rede Interna**, conforme o cenário de testes.
- Foi atribuído IP estático para garantir conectividade com a máquina host.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Configura%C3%A7%C3%A3o%20da%20rede.png)

#### 3. Teste de Conectividade
- Ping da máquina host para a VM e vice-versa.
- Verificação via navegador do painel do Zabbix Appliance (porta 80).

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Testando%20a%20conectividade%20entre%20host%20e%20m%C3%A1quina%20virtual.png)

#### 4. Configuração do Agente SNMP
- O serviço SNMP foi habilitado no host a ser monitorado.
- Parâmetros configurados: comunidade pública, localização e permissões de leitura.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Habilitando%20o%20protocolo%20SNMP.png)

#### 5. Adição do Host no Zabbix
- Inserção manual do endereço IP do host.
- Configuração do tipo de monitoramento via SNMP.
- Aplicação de templates predefinidos.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Adicionando%20host%20no%20Zabbix.png)

#### 6. Visualização de Gráficos
- Gráficos com consumo de CPU, memória, tráfego de rede e disponibilidade de serviços foram disponibilizados.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Gr%C3%A1ficos%20do%20host%20monitorando.png)

---

### ☁️ Zabbix Appliance na AWS

#### 1. Criação do Host
- Instância do Zabbix Appliance foi criada na VPC da AWS.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20do%20Host.png)

#### 2. Regras de Entrada – Segurança
- **SNMP (porta 161)**: habilitada no Security Group para comunicação com os dispositivos.
- **ICMP (ping)**: permitido para verificação de disponibilidade da instância.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20de%20regra%20de%20entrada%20na%20VPC%20(ICMP).png)

#### 3. Configuração do SNMP na Instância Monitorada
- O protocolo SNMP foi configurado dentro da instância Windows Server 2016 na AWS.
- Regras de firewall foram ajustadas.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Configura%C3%A7%C3%A3o%20do%20SNMP%20na%20inst%C3%A2ncia.png)

#### 4. Habilitação no Windows Server Cloud
- Serviços e funcionalidades ativados para permitir gerenciamento remoto.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Windows%20Server%20Cloud%20Host%20habilitado.png)

#### 5. Coleta e Visualização de Dados
- Zabbix mostrou em tempo real as métricas do sistema Windows.
- Itens como uptime, utilização de disco, memória e rede foram monitorados.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Gr%C3%A1ficos%20de%20monitoramento.png)

#### 6. Mapa da Rede (Network Map)
- Criado um mapa com ícones representando a topologia da rede.
- Elementos conectados com status de cor e indicadores visuais (verde, amarelo, vermelho).

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Mapa%20da%20rede.png)

#### 7. Visão Global
- Painel principal do Zabbix com alertas ativos, disponibilidade geral e status de hosts.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Zabbix%20Global%20View.png)

---

### 🛠️ Considerações Finais

O uso do **Zabbix** permite:
- Monitoramento pró-ativo de falhas.
- Geração de alertas automáticos.
- Histórico de métricas para análise de capacidade.
- Integração com ambientes locais e em nuvem.

A configuração de **SNMP** foi essencial para conectar dispositivos diversos, consolidando o sistema de monitoração da infraestrutura da empresa de telemarketing.
