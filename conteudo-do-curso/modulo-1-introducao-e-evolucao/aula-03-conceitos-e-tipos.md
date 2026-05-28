# Aula 03: Conceitos, Funções e Tipos de Sistemas Operacionais

Nesta aula, aprofundamos a definição de Sistema Operacional, explorando suas funções essenciais e a diversidade de tipos de sistemas existentes, desde mainframes até dispositivos embarcados.

---

## 📌 O Sistema Operacional como Intermediário

O SO é o software que gerencia o hardware e fornece serviços para os programas de aplicação. Sua principal função é **abstrair a complexidade do hardware**, permitindo que o programador escreva código sem se preocup same de como cada bit é gravado no disco ou como cada sinal elétrico viaja pela CPU.

### Funções Principais:

| Função | Responsabilidade | Exemplo de Ação |
| :--- | :--- | :--- |
| **Gerenciador de Recursos** | Alocação de hardware | Atribuir 2GB de RAM para o Chrome |
| **Controlador de Dispositivos** | Comunicação via drivers | Traduzir cliques do mouse para o sistema |
| **Provedor de Serviços** | APIs e System Calls | Abrir e salvar um arquivo de texto |

---

## 🖥️ Tipos de Sistemas Operacionais

Dependendo do objetivo, do hardware e do público-alvo, os sistemas operacionais são classificados em diferentes categorias:

### 1. Sistemas de Grande Porte (Mainframes)
Focados em processamento massivo de dados e alta confiabilidade.
- **Uso:** Bancos, seguradoras e processamento de transações governamentais.
- **Características:** Suporte a milhares de usuários simultâneos e alta redundância.

### 2. Sistemas de Servidor
Projetados para fornecer serviços a múltiplos clientes através de uma rede.
- **Exemplos:** Linux (Ubuntu Server, Red Hat), Windows Server.
- **Foco:** Estabilidade, escalabilidade e segurança de rede.

### 3. Sistemas Multiprocessadores
Sistemas que utilizam duas ou mais CPUs trabalhando em conjunto.
- **Vantagens:** Aumento do rendimento (throughput) e maior confiabilidade (se uma CPU falha, outra assume).
- **Desafios:** Sincronização de dados entre núcleos e coerência de cache.

### 4. Sistemas de Computadores Pessoais (Desktops)
Focados na experiência do usuário final e multitarefa.
- **Exemplos:** Windows, macOS, Linux (Ubuntu, Fedora).
- **Foco:** Interface Gráfica (GUI), compatibilidade com softwares diversos e ergonomia.

### 5. Sistemas Operacionais Portáteis (Mobile)
Otimizados para dispositivos com bateria limitada e telas touch.
- **Exemplos:** Android, iOS.
- **Características:** Gerenciamento agressivo de energia e suporte a sensores (GPS, Acelerômetro).

### 6. Sistemas Embarcados (Embedded)
Sistemas dedicados a realizar uma única função específica dentro de um dispositivo maior.
- **Exemplos:** Micro-ondas, Smart TVs, ECU de automóveis.
- **Características:** Baixo consumo de energia, software gravado em ROM/Flash e alta eficiência.

### 7. Sistemas de Nós Sensores
Pequenos dispositivos com recursos extremamente limitados, geralmente em redes.
- **Uso:** Monitoramento agrícola, detecção de incêndios, aplicações militares.
- **Características:** Operação baseada em eventos e consumo mínimo de bateria.

### 8. Sistemas de Tempo Real (Real-Time OS - RTOS)
Sistemas onde o tempo de resposta é a característica mais crítica.
- **Hard Real-Time:** A falha em cumprir o prazo é catastrófica (ex: sistemas de freios ABS, controle de voo).
- **Soft Real-Time:** Atrasos são toleráveis, mas prejudicam a qualidade (ex: streaming de vídeo, jogos).

### 9. Sistemas de Cartões Inteligentes (Smart Cards)
Sistemas com hardware minimalista e foco extremo em segurança.
- **Exemplos:** Chips de cartão de crédito, SIM cards.
- **Características:** Execução de applets criptografados.

---

## 🔧 Introdução ao Git (Ferramenta de Apoio)

Para a organização deste portfólio, utilizamos o **Git**, um sistema de controle de versão distribuído.

### Conceitos Fundamentais:
- **Versionamento:** Permite rastrear cada alteração feita nos arquivos, possibilitando retornar a estados anteriores.
- **Sincronização:** Através do GitHub, é possível compartilhar o código e colaborar com outros desenvolvedores.

### Resumo de Comandos Essenciais:
```bash
# Configuração inicial
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"

# Fluxo básico
git init                # Inicia um repositório local
git add .               # Prepara os arquivos para o commit
git commit -m "Mensagem" # Salva as alterações localmente
git push origin main    # Envia as alterações para o servidor remoto (GitHub)
```
