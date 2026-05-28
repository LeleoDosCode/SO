# Aula 04: Estrutura e Arquitetura de Sistemas Operacionais

Esta aula explora a anatomia interna de um sistema operacional, detalhando como ele organiza seus componentes para gerenciar o hardware e fornecer uma base estável para as aplicações.

---

## 📌 Componentes Fundamentais do SO

Um sistema operacional não é um bloco único de código, mas sim um conjunto de módulos interdependentes:

- **Kernel (Núcleo):** A parte central que gerencia a CPU, memória e dispositivos.
- **Gerenciador de Processos:** Controla a criação, execução e finalização de programas.
- **Gerenciador de Memória:** Aloca e protege o espaço de endereçamento para cada aplicação.
- **Sistema de Arquivos:** Organiza a persistência de dados em volumes de armazenamento.
- **Subsistema de E/S (I/O):** Coordena a comunicação com periféricos.
- **Drivers:** Atuam como tradutores entre o SO e o hardware específico de cada fabricante.

---

## 🧠 O Kernel: O Coração do Sistema

O Kernel é a única parte do sistema com privilégios totais de hardware. Ele é responsável por:
- **Escalonamento:** Decidir qual thread ou processo utiliza a CPU no momento.
- **Gestão de Memória Virtual:** Mapear endereços lógicos para endereços físicos.
- **Sincronização:** Gerenciar locks e semáforos para evitar condições de corrida.
- **Interrupções:** Responder a sinais do hardware (ex: um clique no mouse).

### 🔍 Tipos de Kernel (Aprofundamento)
- **Monolítico:** Todo o sistema (drivers, sistema de arquivos, rede) roda no mesmo espaço de memória. É extremamente rápido, mas se um driver falha, o sistema todo pode travar (ex: Linux).
- **Microkernel:** Apenas as funções essenciais rodam no núcleo; drivers e outros serviços rodam como processos de usuário. É mais estável e seguro, porém ligeiramente mais lento devido à comunicação entre processos (ex: QNX, L4).
- **Híbrido:** Combina a velocidade do monolítico com a modularidade do microkernel (ex: Windows NT).

---

## 🔐 Modos de Execução e Segurança

Para evitar que um erro em um programa (como um navegador) trave todo o computador, o processador utiliza **modos de execução**:

### 1. Modo Usuário (User Mode)
As aplicações rodam neste modo. Elas têm acesso limitado à memória e não podem executar instruções privilegiadas da CPU.

### 2. Modo Kernel (Kernel Mode/Privileged Mode)
Apenas o núcleo do SO opera aqui. Tem acesso total a todo o hardware e memória do sistema.

### 🔄 A Ponte: System Calls (Chamadas de Sistema)
Quando um programa no modo usuário precisa de algo do hardware (ex: ler um arquivo do disco), ele não pode fazer isso diretamente. Ele faz uma **System Call**:
1. O programa solicita o serviço ao SO.
2. O processador alterna do Modo Usuário $\rightarrow$ Modo Kernel.
3. O Kernel valida a solicitação, executa a operação e retorna o resultado.
4. O processador volta para o Modo Usuário.

---

## ⚙️ Processos e Threads

Um **processo** é, simplificadamente, um programa em execução. Ele consiste em:
- **Espaço de Endereçamento:** Memória para o código, dados globais e a pilha (stack).
- **Contexto de CPU:** Valores atuais dos registradores e o contador de programa (PC).
- **Recursos:** Arquivos abertos, sockets de rede e permissões de usuário.

**Diferença entre Processo e Thread:**
- **Processo:** Unidade de isolamento. Possui sua própria memória.
- **Thread:** "Processo leve". Compartilha a memória do processo pai, mas possui sua própria pilha de execução.

---

## 💾 Memória e Espaço de Endereçamento

O SO garante que cada processo opere em seu próprio "mundo virtual".
- **Alocação:** O SO decide onde colocar o programa na RAM física.
- **Proteção:** Impede que o Processo A escreva na memória do Processo B.
- **Isolamento:** Essencial para a estabilidade do sistema; se um processo falha, ele não derruba os outros.

---

## 📁 Sistemas de Arquivos e Drivers

O SO abstrai a complexidade física do armazenamento. Em vez de lidar com setores e trilhas do disco, o usuário lida com **pastas e arquivos**.
- **Hierarquia:** Organização em árvore para facilitar a localização.
- **Metadados:** Informações sobre data de criação, tamanho e permissões.

**Drivers de Dispositivo:**
São módulos que "ensinam" o kernel a falar com um hardware específico. Eles traduzem comandos genéricos do SO (ex: `imprimir_documento()`) em sinais elétricos que a impressora entende.

---

## 🔄 Reaproveitamento de Estruturas

Raramente um SO moderno é escrito do zero. A indústria utiliza bases estáveis para criar novas distribuições:
- **Exemplos de Derivações:**
  - **Debian $\rightarrow$ Ubuntu $\rightarrow$ Linux Mint.**
  - **FreeBSD $\rightarrow$ Orbis OS (PS4).**
  - **Linux $\rightarrow$ Android.**

**Vantagens do Reaproveitamento:**
1. **Estabilidade:** O kernel base já foi testado em milhões de máquinas.
2. **Custo:** Redução drástica no tempo de desenvolvimento.
3. **Compatibilidade:** Suporte a drivers já existentes.
