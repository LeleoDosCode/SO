# Estudo de Caso: Planejamento de Infraestrutura para a DevStore

Este documento apresenta a proposta de modernização da infraestrutura da startup **DevStore**, aplicando conceitos de Sistemas Operacionais, Virtualização e Cloud Computing.

---

## 🚨 1. Diagnóstico da Situação Atual

A DevStore opera com um modelo de "TI artesanal", apresentando os seguintes gargalos:
- **Falta de Padronização:** Cada desenvolvedor usa sua própria máquina para testes, gerando o erro "na minha máquina funciona".
- **Risco Operacional:** Ausência de versionamento de código e backups automatizados.
- **Escalabilidade Zero:** Para crescer a capacidade de atendimento, precisariam comprar hardware físico e configurá-lo manualmente.
- **Insegurança:** Ambientes de desenvolvimento, teste e produção estão misturados.

---

## 🏗️ 2. Proposta de Arquitetura Moderna

A solução proposta divide a infraestrutura em camadas lógicas, garantindo isolamento e reprodutibilidade.

### 🔹 Camada de Desenvolvimento (Local)
Implementação de **Containerização com Docker**.
- **Solução:** Cada projeto terá seu próprio `Dockerfile` e `docker-compose.yml`.
- **Resultado:** O ambiente de desenvolvimento será idêntico ao de produção, eliminando inconsistências.
- **Controle:** Versionamento obrigatório via **Git**.

### 🔹 Camada de Validação (Staging)
Criação de um ambiente de espelhamento utilizando **Virtualização**.
- **Solução:** Uso de VMs isoladas para testar atualizações do SO e patches de segurança antes do deploy final.
- **Resultado:** Maior estabilidade e redução de bugs em produção.

### 🔹 Camada de Produção (Nuvem)
Migração para a **AWS (Amazon Web Services)** utilizando modelos híbridos.
- **Computação:** Instâncias EC2 (IaaS) para controle total do SO ou serviços de containers (ECS/EKS).
- **Escalabilidade:** Implementação de *Auto Scaling* para aumentar o número de instâncias automaticamente durante picos de acesso.
- **Disponibilidade:** Distribuição de instâncias em múltiplas Zonas de Disponibilidade (AZs).

---

## 🔐 3. Estratégia de Segurança e Monitoramento

Para garantir a integridade dos dados e a estabilidade do sistema:

1. **RBAC (Role-Based Access Control):** Controle de acesso baseado em funções. Desenvolvedores não têm acesso root ao servidor de produção.
2. **Firewalls e VPC:** Isolamento da rede de produção em uma Nuvem Privada Virtual (VPC).
3. **Observabilidade:** Implementação de dashboards de monitoramento (CPU, RAM, Latência) para identificar gargalos antes que causem quedas.

---

## ⚖️ 4. Justificativa Técnica

| Tecnologia | Impacto na DevStore | Justificativa de SO |
| :--- | :--- | :--- |
| **Docker** | Padronização | Isolamento de processos e bibliotecas via containers. |
| **Virtualização** | Segurança | Separação total de kernels para testes críticos. |
| **AWS Cloud** | Escalabilidade | Abstração de hardware físico para recursos elásticos. |
| **CI/CD** | Agilidade | Automação do fluxo: Código $\rightarrow$ Teste $\rightarrow$ Deploy. |

---

## 🏁 5. Conclusão e Reflexões Finais

A modernização da DevStore não é apenas uma troca de ferramentas, mas uma mudança de paradigma operacional. Ao migrar de um modelo manual para um ambiente **automatizado, escalável e seguro**, a startup resolve a dívida técnica de infraestrutura.

A aplicação de conceitos de Sistemas Operacionais — como o isolamento de processos via containers e a abstração de hardware via nuvem — garante que a empresa possa crescer sem que a complexidade do SO se torne um impedimento. O resultado final é um ecossistema onde a estabilidade do Kernel e a eficiência da virtualização suportam a agilidade do negócio.
