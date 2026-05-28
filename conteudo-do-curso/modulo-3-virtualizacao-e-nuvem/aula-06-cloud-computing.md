# Aula 06: Computação em Nuvem e Sistemas Operacionais

A computação em nuvem (Cloud Computing) é a evolução natural da virtualização. Enquanto a virtualização nos permite criar máquinas virtuais, a nuvem nos permite consumir esses recursos como serviços via internet.

---

## ☁️ 1. Fundamentos da Nuvem

A computação em nuvem é a entrega de recursos computacionais (CPU, armazenamento, banco de dados, rede) sob demanda, com pagamento baseado no uso (**pay-per-use**).

### Características Essenciais (Modelo NIST):
- **Autoatendimento sob demanda:** O usuário provisiona recursos sem precisar de interação humana com o provedor.
- **Acesso amplo à rede:** Acesso via web de qualquer dispositivo.
- **Pool de Recursos:** O hardware físico é compartilhado entre milhares de usuários (multi-tenancy).
- **Elasticidade Rápida:** Capacidade de aumentar ou diminuir recursos instantaneamente conforme a demanda.
- **Serviço Mensurável:** Controle rigoroso do consumo para fins de cobrança.

**Transição Financeira:** Mudança de **CAPEX** (Capital Expenditure - compra de hardware caro) para **OPEX** (Operational Expenditure - custo operacional mensal).

---

## 🖥️ 2. A Relação entre o SO e a Nuvem

O Sistema Operacional continua sendo a base, mas sua implementação na nuvem muda radicalmente.

### O Papel do Hypervisor
A nuvem baseia-se em hypervisors massivos que gerenciam milhares de VMs em clusters de servidores. O SO convidado (Guest) não sabe que está na nuvem; ele opera normalmente, mas seus recursos são limitados e controlados pelo provedor.

### Modelos de Serviço (SPI)

| Modelo | Nome | Descrição | Exemplo |
| :--- | :--- | :--- | :--- |
| **IaaS** | Infrastructure as a Service | O provedor dá o hardware virtual. Você instala o SO, configura a rede e as apps. | AWS EC2, Azure VM |
| **PaaS** | Platform as a Service | O provedor gerencia o SO e o runtime. Você apenas envia o código da aplicação. | Render, Heroku, Vercel |
| **SaaS** | Software as a Service | O software é entregue pronto via navegador. Você não gerencia nada da infra. | Google Workspace, Netflix |

---

## 🌐 3. Modelos de Implantação

- **Nuvem Pública:** Recursos compartilhados entre várias empresas. Menor custo e maior escalabilidade.
- **Nuvem Privada:** Infraestrutura dedicada a uma única organização. Maior controle e segurança.
- **Nuvem Híbrida:** Combinação de ambas. Dados sensíveis ficam na privada, e o processamento pesado na pública.

---

## 🔐 4. Segurança e Responsabilidade Compartilhada

Um conceito crucial na nuvem é o **Modelo de Responsabilidade Compartilhada**:
- **Segurança DA Nuvem (Provedor):** O provedor garante a segurança física do datacenter, a eletricidade e o hypervisor.
- **Segurança NA Nuvem (Cliente):** O usuário é responsável por configurar firewalls, atualizar o SO da VM, gerenciar senhas e criptografar os dados.

---

## 📦 5. Containers e Microsserviços

A virtualização tradicional (VMs) é pesada pois cada VM exige um SO completo. Para resolver isso, surgiram os **Containers**.

### Docker vs VM
- **VM:** Simula o hardware $\rightarrow$ Exige SO completo $\rightarrow$ Lenta para iniciar $\rightarrow$ Consome muita RAM.
- **Container:** Compartilha o kernel do SO hospedeiro $\rightarrow$ Apenas as bibliotecas da app $\rightarrow$ Inicia em milissegundos $\rightarrow$ Extremamente leve.

**Microsserviços:** É a arquitetura de dividir uma aplicação gigante em pequenos serviços independentes (cada um em seu container), facilitando a escalabilidade e a manutenção.
