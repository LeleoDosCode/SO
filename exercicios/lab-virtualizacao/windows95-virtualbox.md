# Lab de Virtualização: Implementação do Windows 95 no VirtualBox

Este documento detalha o processo técnico de virtualização de um sistema legado, analisando a interação entre o hardware simulado e o software antigo.

---

## 🧠 Objetivo do Experimento

Demonstrar a capacidade de abstração de hardware através da criação de uma máquina virtual rodando o **Windows 95**, correlacionando a prática com os conceitos de gerenciamento de recursos e isolamento de sistemas.

---

## 🛠️ 1. Setup do Ambiente

Para este laboratório, foram utilizados:
- **Hypervisor:** Oracle VirtualBox.
- **SO Hospedeiro (Host):** Windows 10/11.
- **SO Convidado (Guest):** Windows 95 (via ISO).

---

## 💻 2. Configuração da Máquina Virtual (VM)

Diferente de sistemas modernos, o Windows 95 exige configurações modestas, mas específicas:

| Componente | Configuração | Justificativa |
| :--- | :--- | :--- |
| **Nome** | `Windows95-VM` | Identificação do ambiente |
| **Tipo** | Microsoft Windows | Definição de drivers base |
| **Versão** | Windows 95 | Otimização de BIOS e hardware |
| **RAM** | 64 MB | Suficiente para a época; excesso pode causar instabilidade |
| **Disco (VDI)** | 2 GB | Dinamicamente alocado para economizar espaço no host |

---

## 📀 3. Processo de Instalação

1. **Montagem:** A ISO do Windows 95 foi inserida no drive óptico virtual.
2. **Boot:** A VM iniciou o processo de leitura da imagem ISO.
3. **Particionamento:** Criação da partição FAT16 no disco virtual.
4. **Configuração:** Definição de idioma e nome do computador.
5. **Finalização:** Inicialização da interface gráfica clássica.

---

## 🔍 4. Análise Técnica e Observações (Conceitos de SO)

### 🔹 Abstração de Hardware
O VirtualBox simulou componentes de hardware de 1995. O Windows 95 "acredita" estar lidando com um processador Pentium e memória EDO, embora esteja rodando em um hardware moderno.

### 🔹 Host vs Guest
- **Soberania do Host:** O sistema hospedeiro detém o controle total. Se o processo do VirtualBox for encerrado, o Windows 95 "desliga" instantaneamente.
- **Isolamento:** Qualquer alteração feita no sistema de arquivos do Windows 95 ocorre apenas dentro do arquivo `.vdi`, sem risco para o host.

### 🔹 Gerenciamento de Recursos
A CPU real do computador é compartilhada. O Windows 95 executa seus processos em threads gerenciadas pelo hypervisor, que as traduz para a CPU física.

---

## 📊 Conclusão

A virtualização do Windows 95 evidencia a evolução dos sistemas operacionais. Enquanto o Windows 95 tinha acesso quase direto ao hardware (pouca abstração), a VM moderna coloca várias camadas de tradução entre o software e o silício.

Este experimento comprova que a virtualização é a ferramenta ideal para preservação de software legado e estudos de arquitetura de sistemas.
