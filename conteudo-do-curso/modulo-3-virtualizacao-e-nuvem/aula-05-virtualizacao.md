# Aula 05: Introdução à Virtualização

A virtualização é a tecnologia que permite a criação de representações virtuais de recursos de hardware, permitindo que múltiplos sistemas operacionais coexistam no mesmo hardware físico de forma isolada.

---

## 📌 O que é Virtualização?

Em termos simples, a virtualização cria uma camada de abstração entre o hardware físico e o sistema operacional. Essa camada simula os componentes de hardware (CPU, RAM, Disco, Rede), permitindo que o software "acredite" que está rodando em uma máquina real.

### Conceitos Chave:
- **Host (Hospedeiro):** A máquina física real e o sistema operacional que nela roda.
- **Guest (Convidado):** A máquina virtual (VM) que roda dentro do host.
- **Hypervisor (VMM - Virtual Machine Monitor):** O software responsável por criar, gerenciar e alocar recursos para as VMs.

---

## ✅ Vantagens da Virtualização

1. **Consolidação de Hardware:** Redução de custos ao rodar vários servidores em um único hardware potente.
2. **Isolamento e Segurança:** Se uma VM for infectada por um vírus ou travar, o host e as outras VMs permanecem intactos.
3. **Snapshots e Recuperação:** Capacidade de salvar o estado exato de uma VM e restaurá-lo instantaneamente se algo der errado.
4. **Multiplataforma:** Permite rodar Windows dentro do Linux, ou testar versões antigas de SOs sem precisar de hardware legado.

---

## 🧰 Ferramenta de Estudo: Oracle VirtualBox

O VirtualBox é um hypervisor de **Tipo 2** (roda sobre um sistema operacional já existente).

### Componentes de Configuração da VM:
- **Memória RAM:** Alocação de uma fatia da RAM real para a VM.
- **Armazenamento VDI (Virtual Disk Image):** Um arquivo no disco do host que funciona como o HD da VM.
- **Rede (NAT/Bridge):** Define como a VM se comunica com a internet e com o host.
- **ISO:** Imagem do disco de instalação do sistema operacional.

---

## 🐧 Estudo de Caso: Tiny Core Linux

Para fins de teste, utilizamos o **Tiny Core Linux**, uma distribuição minimalista.
- **Objetivo:** Demonstrar a agilidade de boot e o baixo consumo de recursos.
- **Lição:** Mostrar que a virtualização é eficiente mesmo para sistemas extremamente leves, consumindo frações mínimas da RAM do host.

---

## 📝 Atividade Proposta

O objetivo é a instalação e configuração de um ambiente virtualizado seguindo estes passos:
1. Instalação do Hypervisor (VirtualBox).
2. Criação de uma VM com especificações de hardware adequadas ao SO convidado.
3. Montagem de ISO e instalação do sistema.
4. Documentação do processo através de um manual técnico.
