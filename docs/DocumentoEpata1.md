# 📘 Projeto de Infraestrutura de Rede – Empresa de Telemarketing

## 1. Tema

Empresa de telemarketing com sede na capital e suporte a funcionários em **home office**.

---

## 2. Objetivos do Negócio

- **Escalabilidade**: Suportar crescimento de agentes e volume de chamadas.
- **Redução de Custos**: Uso de VoIP e recursos em nuvem.
- **Segurança e Conformidade**: Adequação à LGPD.
- **Qualidade de Chamadas**: Voz clara e estável.
- **Vantagem Competitiva**: Rede como diferencial.
- **Produtividade dos Agentes**: CRM e roteamento inteligente.
- **Redução de Espera**: Foco na agilidade do atendimento.
- **Análise em Tempo Real**: Dashboards e monitoramento contínuo.
- **Integração Omnicanal**: Chat, e-mail, voz, redes sociais.
- **Alta Disponibilidade**: Redundância e resiliência da rede.
- **Satisfação do Cliente**: Coleta de feedback contínua.

---

## 3. Características da Empresa

| Unidade        | Nº de Funcionários |
|----------------|--------------------|
| Sede Principal | 300                |
| Filial 1       | 100                |
| Filial 2       | 50                 |

- Operadores usam **VoIP** e **CRM**.
- Supervisores e TI usam **monitoramento**, **dashboards** e **e-mail corporativo**.

---

## 4. Necessidades de Infraestrutura

### 📌 Escritório Físico

- Rede cabeada e Wi-Fi corporativa.
- Segmentação por departamentos.
- Firewall e controle de acesso.
- QoS para priorização de VoIP.
- Redundância de conexão.

### 🏡 Home Office

- Monitoramento de qualidade de conexão.
- Recomendação de banda mínima.
- Treinamento de segurança cibernética.
- Suporte técnico remoto.

---

## 5. Desafios Previstos

- Instabilidade em chamadas VoIP.
- Lentidão no CRM.
- Sincronização de dados entre sede e filiais.

---

## 6. Fontes e Destinos do Tráfego

| Comunidade            | Localização     | Aplicações Utilizadas          |
|-----------------------|------------------|--------------------------------|
| Operadores (Sede)     | Sede Principal   | VoIP, CRM, Webmail             |
| Operadores (Filial 1) | Filial 1         | VoIP, CRM, Webmail, VPN        |
| Operadores (Filial 2) | Filial 2         | VoIP, CRM, Webmail             |
| Supervisores          | Todas unidades   | CRM, Dashboards, Webmail       |
| TI e Infraestrutura   | Todas unidades   | Monitoramento, Backup, VPN     |

---

## 7. Fluxos de Tráfego

- **Cliente-Servidor**: Operadores ↔ CRM e VoIP.
- **Servidor-Servidor**: Sincronização e backup.
- **Acesso à Nuvem**: Dashboards e análise.

---

## 8. Características do Tráfego

| Aplicação  | Protocolo | Tipo de Fluxo    | QoS       | Taxa de Dados |
|------------|-----------|------------------|-----------|----------------|
| VoIP       | UDP       | Cliente-Servidor | Muito Alta| Média           |
| CRM        | TCP       | Cliente-Servidor | Alta      | Alta            |
| VPN        | TCP       | Servidor-Servidor| Alta      | Média           |
| Dashboards | HTTP/HTTPS| Cliente-Servidor | Média     | Baixa           |

---

## 9. Requisitos Técnicos

- Disponibilidade da rede ≥ 99,5% ao ano.
- Delay máximo: 3000 ms.
- Firewall e IDS ativos 100% do tempo.
- Escalabilidade para +50% do tráfego normal.
- Redundância dupla em pontos críticos.
- Redes separadas para voz, vídeo e dados.
- Acesso via VPN para home office.
- Rede descentralizada.

---

## 10. Restrições do Projeto

1. Infraestrutura baseada em **nuvem**.
2. Preferência por **open-source** ou soluções de **baixo custo**.
3. Suporte a chamadas de **vídeo** com fluidez.
4. Limite de dispositivos por cargo.
5. Uso exclusivo de **máquinas corporativas**.

---

## 11. Inventário – Equipamentos da Matriz

### 🖥️ Equipamentos Técnicos

- **Computadores**: Lenovo ThinkCentre Neo 50s
- **Monitores**: ThinkVision 21.5”
- **Servidores**: DELL PowerEdge R450
- **Switches**: Cisco CBS220-24T-4X
- **Roteador**: Huawei S380-H8T3ST
- **Rack Servidor**: 36U Max Eletron

### 🧩 Infraestrutura

- Patch Panels Cat6 (Furukawa)
- Patch Cords 2m Cat6 (Furukawa)
- Keystone RJ45
- Cabos de rede Cat6
- Mesas, cadeiras e headsets USB

---
