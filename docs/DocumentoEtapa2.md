## Etapa 2: Preparação do Ambiente em Nuvem e Virtualização Local

### Virtualização Local

A etapa de virtualização local teve como objetivo estruturar um ambiente de rede corporativa simulado com uso do **Windows Server 2012**, configurado com os seguintes serviços:

- **Active Directory (AD)**
- **DNS (Domain Name System)**
- **GPO (Group Policy Objects)**

Esses serviços permitem:
- Gerenciamento centralizado de recursos e usuários
- Aplicação de políticas de segurança
- Controle de dispositivos e autenticação de usuários

#### Passos Realizados

1. **Instalação do Windows Server 2012**
   - O sistema foi instalado em uma máquina virtual no Oracle VirtualBox.

2. **Configuração Inicial**
   - Nome do servidor alterado para `Server01`.
   - Conexões remotas habilitadas.

   ![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Configura%C3%A7%C3%A3o%20inicial%20do%20servidor.png)

3. **Instalação e Configuração do DNS**
   - Pré-requisito para o funcionamento do AD.
   - Permite resolução de nomes no domínio interno.

4. **Configuração do Active Directory**
   - O servidor foi promovido a **Controlador de Domínio**.
   - Criada floresta com domínio raiz: `telemarketing.net`.

   ![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Configura%C3%A7%C3%A3o%20do%20Active%20Directory%20(AD).png)

5. **Estrutura Organizacional do Domínio**
   - Criadas Unidades Organizacionais (UOs) representando:
     - Matriz
     - Filial 1
     - Filial 2

   ![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Estrutura%20Organizacional%20do%20Dom%C3%ADnio.png)

6. **Criação de Usuários e Grupos**
   - Simulação dos funcionários com usuários e grupos fictícios.

   ![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20de%20Usu%C3%A1rios%20e%20Grupos.png)

7. **Criação e Aplicação de GPOs**
   - Políticas específicas para UOs, como:
     - Restrições de acesso
     - Regras de segurança
     - Configurações específicas para Windows 8.1

   ![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20e%20Configura%C3%A7%C3%A3o%20de%20Pol%C3%ADticas%20de%20Grupo%20(GPO).png)

---

### Preparação do Ambiente em Nuvem

A infraestrutura em nuvem foi desenvolvida utilizando a **AWS (Amazon Web Services)**, focando na criação de uma rede segura e escalável para suportar as operações da empresa de telemarketing.

#### Passos Realizados

1. **Criação da VPC (Virtual Private Cloud)**
   - Define bloco de IPs, sub-redes e regras de segurança.
   - Proporciona isolamento e controle do tráfego interno.
   
![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20da%20VPC.png)

2. **Configuração do Security Group**
   - Define regras de entrada e saída para os recursos da nuvem.
   - Garante controle sobre o acesso aos servidores.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20do%20Security%20Group.png)

3. **Criação do Servidor na VPC**
   - Instância do **Windows Server 2016** configurada.
   - Utilizada como ambiente de testes e demonstração.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Cria%C3%A7%C3%A3o%20do%20servidor%20dentro%20da%20VPC.png)

4. **Validação**
   - Testes foram realizados para confirmar o funcionamento das configurações dentro da instância criada.

![png](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-1-pe5-t2-g3-teleconnect/blob/main/docs/Valida%C3%A7%C3%A3o%20das%20altera%C3%A7%C3%B5es%20no%20arquivo%20em%20execu%C3%A7%C3%A3o%20na%20inst%C3%A2ncia.png)

---

### Considerações

A combinação de ambiente virtualizado local e nuvem oferece:
- Maior **flexibilidade**
- **Gerenciamento centralizado**
- **Escalabilidade** para crescer com a demanda
- **Segurança** robusta
- Suporte eficiente a colaboradores **remotos e presenciais**
