# Aula 07: Desenvolvimento de APIs e Deploy em Nuvem

Nesta aula, unimos os conceitos de backend, APIs REST e infraestrutura de nuvem para colocar aplicações reais em produção.

---

## 🚀 1. APIs REST com Node.js e Express

Uma **API REST (Representational State Transfer)** é um conjunto de regras que permite que dois sistemas se comuniquem via protocolo HTTP.

### Ferramentas Utilizadas:
- **Node.js:** Ambiente de execução JavaScript no servidor. [Documentação Oficial](https://nodejs.org/docs/)
- **Express.js:** Framework minimalista para criar rotas e gerenciar requisições HTTP. [Documentação Express](https://expressjs.com/)
- **CORS (Cross-Origin Resource Sharing):** Mecanismo de segurança que permite que o frontend (em um domínio) acesse o backend (em outro domínio).

### Fluxo de Requisição:
`Cliente (Browser) $\xrightarrow{GET /status}$ Servidor (Express) $\xrightarrow{Lê Dados do SO}$ Resposta (JSON)`

---

## ☁️ 2. A Plataforma Render

O **Render** é um serviço de **PaaS (Platform as a Service)** que automatiza o ciclo de vida da aplicação.

### Fluxo de Deploy Automatizado:
1. **Código no GitHub:** O desenvolvedor faz o `git push`.
2. **WebHook:** O GitHub avisa o Render que há código novo.
3. **Build:** O Render baixa o código, roda `npm install` e prepara a aplicação.
4. **Start:** O Render executa `node index.js` e disponibiliza uma URL pública com SSL (HTTPS).

---

## 📊 3. Monitoramento de Sistemas via API

O uso do módulo `os` do Node.js permite que nossa API atue como um sensor do sistema operacional, expondo métricas em tempo real:

- **Hostname:** Identifica a máquina na rede.
- **Plataforma:** Identifica se o SO é `win32` (Windows) ou `linux`.
- **CPU & RAM:** Monitora a carga de processamento e o consumo de memória.
- **Uptime:** Indica há quanto tempo o sistema está ligado sem reiniciar.

---

## ⚖️ 4. Comparação de Ambientes: Local vs Nuvem

Ao fazer o deploy, observamos diferenças fundamentais no comportamento do SO:

| Métrica | Ambiente Local (Desktop) | Ambiente Cloud (SaaS/PaaS) |
| :--- | :--- | :--- |
| **Recursos** | Dedicados (ex: 16GB RAM) | Compartilhados/Limitados (ex: 512MB) |
| **OS** | Windows / macOS | Quase sempre Linux (Ubuntu/Debian) |
| **Persistência** | Arquivos gravados no HD real | Sistemas de arquivos efêmeros (voláteis) |
| **Acesso** | `localhost:3000` | `https://app.onrender.com` |

---

## ⚠️ 5. A Natureza Serverless (Vercel)

Diferente do Render, plataformas como a **Vercel** utilizam arquitetura **Serverless (Funções como Serviço)**.

**O que isso significa para o SO?**
- A aplicação não fica "rodando" o tempo todo.
- Ela "acorda" apenas quando recebe uma requisição e "dorme" logo depois.
- **Impacto:** Monitoramentos contínuos (como loops de CPU) não funcionam bem, pois o processo é interrompido entre as chamadas.
