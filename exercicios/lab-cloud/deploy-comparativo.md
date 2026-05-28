# Lab de Nuvem: Deploy Comparativo e Análise de Plataformas

Este laboratório documenta a experiência de deploy de uma aplicação de monitoramento de SO em duas plataformas distintas: **Render** e **Vercel**, analisando a diferença entre arquiteturas de containers e serverless.

---

## 🚀 1. Implementação da Aplicação

Foi desenvolvida uma API em **Node.js + Express** que utiliza o módulo `os` para extrair métricas do sistema operacional em tempo real.

**Métricas monitoradas:**
- Hostname e Plataforma.
- Uso de CPU e Memória RAM.
- Tempo de atividade (Uptime).

---

## ☁️ 2. Análise de Deploy: Render (PaaS/Containers)

O deploy no Render foi realizado via integração direta com o GitHub.

- **Comportamento:** A aplicação roda dentro de um container Linux persistente.
- **Observação:** As métricas de memória e CPU são estáveis e refletem a alocação do container.
- **Veredito:** Ideal para APIs REST e aplicações que exigem execução contínua (background processes).

---

## ⚡ 3. Análise de Deploy: Vercel (Serverless)

O deploy na Vercel seguiu o mesmo fluxo de integração com GitHub.

- **Comportamento:** A aplicação é convertida em "Serverless Functions".
- **Observação:** A aplicação "morre" após responder a requisição. Não existe um "uptime" real do servidor, apenas da função.
- **Veredito:** Ideal para Frontends (React, Next.js) e APIs simples que não exigem estado persistente.

---

## 📊 4. Tabela Comparativa Final

| Característica | Render | Vercel |
| :--- | :--- | :--- |
| **Arquitetura** | Container Linux | Serverless Functions |
| **Persistência** | Alta (Processo contínuo) | Baixa (Execução sob demanda) |
| **Uso de CPU** | Monitorável em tempo real | Fragmentado por requisição |
| **Uptime** | Consistente | Efêmero |
| **Indicação** | Backends e APIs Complexas | Frontends e Micro-serviços |

---

## 🧠 5. Conclusão Técnica

A atividade demonstrou que a escolha da plataforma de nuvem impacta diretamente a forma como a aplicação interage com o Sistema Operacional. Enquanto o **Render** nos fornece um ambiente que simula um servidor tradicional (com kernel e processos persistentes), a **Vercel** abstrai completamente o SO, entregando apenas a execução do código.

Para sistemas de monitoramento de infraestrutura, a abordagem de containers (Render) é a única viável, pois requer a persistência do processo para coleta de métricas.
