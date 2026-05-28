# Aula 01: Apresentação da Disciplina e Introdução aos Sistemas Operacionais

## 👨‍🏫 Docência
**Professor:** Prof. Me. Deivison S. Takatu

---

## 🎯 Objetivos da Aula
Esta aula introdutória visa situar o aluno no contexto da disciplina, apresentando a organização do curso e os fundamentos básicos de Sistemas Operacionais (SO).

**Tópicos abordados:**
- Contextualização da disciplina e plano de ensino.
- Metodologia de trabalho e critérios de avaliação.
- Definições fundamentais de Sistemas Operacionais.

---

## 💻 Fundamentos de Sistemas Operacionais (SO)

### 1. Definição
Um **Sistema Operacional** é a camada de software fundamental que atua como intermediária entre o hardware do computador e o usuário/aplicações. Ele é responsável por gerenciar todos os recursos do sistema, garantindo que o hardware seja utilizado de forma eficiente e segura.

### 2. Importância e Funções
- **Interface Homem-Máquina:** Permite que o usuário interaja com o hardware sem precisar conhecer a complexidade eletrônica subjacente.
- **Gerenciamento de Recursos:** Controla quem usa a CPU, quanta memória é alocada e como os dados são gravados no disco.

### 3. Exemplos Comuns
- **Desktops:** Windows, macOS, Linux.
- **Móbiles:** Android, iOS.

---

## 🏗️ Arquitetura e Estrutura dos SOs

### Estrutura em Camadas
Os sistemas modernos são organizados de forma hierárquica (camadas), o que facilita a modularidade e a manutenção do código.

### O Kernel (Núcleo)
O **Kernel** é a parte central do sistema operacional. Ele reside permanentemente na memória e possui controle total sobre o hardware.
- **Kernel Monolítico:** Todas as funções (sistema de arquivos, drivers, gerenciamento de memória) rodam em um único espaço de endereço.
- **Kernel Modular:** Permite carregar e descarregar módulos dinamicamente, aumentando a flexibilidade.

### Modos de Operação
Para garantir a estabilidade, o processador opera em diferentes níveis de privilégio:
- **Modo Usuário:** Onde as aplicações comuns rodam. O acesso ao hardware é restrito.
- **Modo Kernel:** Onde o SO executa funções críticas. Possui acesso total a todas as instruções da CPU e periféricos.

---

## ⏱️ Escalonamento de Processos

O escalonador decide qual processo terá acesso à CPU e por quanto tempo.
- **Objetivos:** Maximizar a eficiência (throughput), garantir justiça entre os processos e minimizar o tempo de resposta.
- **Algoritmos Comuns:**
  - **FIFO (First-In, First-Out):** O primeiro a chegar é o primeiro a ser servido.
  - **Round Robin:** Cada processo recebe um "quantum" (fatia) de tempo.
  - **Prioridade:** Processos mais importantes são executados primeiro.

---

## 🧠 Gerenciamento de Memória

### Memória Principal (RAM)
O SO deve alocar espaço para cada programa e garantir que um processo não acesse a memória de outro (proteção de memória).

### Memória Virtual
Técnica que permite que o computador execute programas maiores que a sua memória RAM física, utilizando parte do disco como extensão da memória (paginação e segmentação).

---

## 📂 Gerenciamento de Recursos e Segurança

- **E/S (Entrada e Saída):** Controle de drivers para teclados, mouses, discos e redes.
- **Sistemas de Arquivos:** Organização lógica de dados em diretórios e arquivos.
- **Segurança:** Implementação de permissões de acesso e proteção contra ameaças externas.
- **Virtualização:** Criação de representações virtuais de hardware para otimizar o uso de servidores.

---

## 📁 O Valor do Portfólio Acadêmico
A manutenção de um repositório organizado (como este no GitHub) é fundamental para o desenvolvimento profissional, pois:
1. **Comprova Competências:** Demonstra que o aluno domina as ferramentas e conceitos.
2. **Organização:** Reflete a capacidade de documentar e estruturar projetos.
3. **Visibilidade:** Facilita a inserção no mercado de trabalho e estágios.

---

## 📝 Sistema de Avaliação
A nota final da disciplina é composta por:
$\text{Nota Final} = (P_1 \times 0,25) + (P_2 \times 0,25) + ((PJ + AT) \times 0,25)$

- **P1/P2:** Provas teóricas.
- **PJ:** Projeto Prático.
- **AT:** Atividades complementares.

---

## 👥 Dinâmica de Trabalho
- Grupos de 3 a 5 integrantes.
- Entregas via GitHub em formato Markdown.
- Uso de ferramentas de design (Miro) para linha do tempo.

---

## 📚 Referências Bibliográficas
- TANENBAUM, A. S.; BOS, H. **Sistemas Operacionais Modernos**, 2016.
- SILBERSCHATZ, A. et al. **Fundamentos de Sistemas Operacionais**, 2015.
- STALLINGS, W. **Sistemas Operacionais: Conceitos e Projetos**, 2015.
- DENARDIN, G. W.; BARRIQUELLO, C. H., 2014.
