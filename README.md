# 🏥 Clinic Queue Scheduling System

Implementação em **Java puro** para simulação de agendamento e triagem de uma clínica médica, aplicando conceitos fundamentais de **Tipos Abstratos de Dados (TAD)**, **Programação Orientada a Objetos (POO)** e estruturas de **filas estáticas e dinâmicas**.

---

## 🎯 Regras de Negócio e Estruturas de Dados

O sistema simula dois fluxos de atendimento com diferentes regras de negócio e requisitos de gerenciamento de memória:

| Fluxo                         | Regra de Atendimento                                     | Estrutura de Dados                               | Justificativa Técnica                                                                                     |
| ----------------------------- | -------------------------------------------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| **Consultas Médicas**         | Máximo de 5 agendamentos por dia                         | Fila Estática (`ListaEstatica.java`)             | Capacidade delimitada por array, permitindo controle explícito de overflow e respeito ao limite definido. |
| **Atendimento de Enfermagem** | Atendimento 24h, sem limite pré-definido de agendamentos | Fila Dinâmica (`ListaDinamica.java` / `No.java`) | Utiliza nós encadeados alocados dinamicamente em memória, permitindo crescimento conforme a demanda.      |

---

## 🛠️ Tecnologias e Conceitos

### Tecnologia

* **Java SE**
* Compilação utilizando `javac`
* Execução via linha de comando

### Conceitos aplicados

* Tipos Abstratos de Dados (TAD)
* Programação Orientada a Objetos (POO)
* Estruturas de dados
* Filas (FIFO)
* Alocação estática de memória
* Alocação dinâmica de memória
* Nós encadeados
* Manipulação de referências em Java
* Controle de capacidade e overflow
* Modelagem de domínio

---

## 📂 Arquitetura dos Arquivos

```text
clinic-queue-scheduler-java/
│
├── Agendamento.java
├── No.java
├── ListaEstatica.java
├── ListaDinamica.java
├── TestaAgendamento.java
└── README.md
```

### Descrição dos componentes

#### `Agendamento.java`

Modelo de domínio responsável por representar um agendamento e seus dados relacionados ao paciente/atendimento.

#### `No.java`

Representa o elemento básico utilizado na estrutura de fila dinâmica, mantendo a referência para o próximo nó da sequência.

#### `ListaEstatica.java`

Implementação da fila estática utilizando um **array**, com capacidade previamente definida.

É utilizada para representar o fluxo de **consultas médicas**, que possui limite de cinco agendamentos por dia.

#### `ListaDinamica.java`

Implementação de uma fila dinâmica baseada em **nós encadeados**, permitindo que a estrutura cresça conforme a necessidade.

É utilizada no fluxo de **atendimento de enfermagem**, que não possui um limite fixo de agendamentos.

#### `TestaAgendamento.java`

Classe executável responsável pela simulação dos agendamentos e pelos testes dos diferentes fluxos de atendimento.

---

## ⚙️ Como Compilar e Executar

O projeto não utiliza frameworks ou gerenciadores de dependências. A compilação pode ser realizada diretamente pelo compilador Java.

### 1. Clone o repositório

```bash
git clone https://github.com/aleroberto/clinic-queue-scheduler-java.git
```

### 2. Acesse o diretório

```bash
cd clinic-queue-scheduler-java
```

### 3. Compile os arquivos Java

```bash
javac *.java
```

### 4. Execute a aplicação

```bash
java TestaAgendamento
```

---

## 🧠 Estruturas de Dados

### Fila Estática

A fila estática utiliza um array com capacidade previamente definida.

Neste projeto, essa estrutura representa o fluxo de **consultas médicas**, no qual existe uma restrição de até **5 agendamentos por dia**.

```text
[Paciente 1] → [Paciente 2] → [Paciente 3] → [Paciente 4] → [Paciente 5]
                                                               ↑
                                                        capacidade máxima
```

Quando a capacidade máxima é atingida, novos agendamentos não podem ser inseridos.

### Fila Dinâmica

A fila dinâmica utiliza nós encadeados, permitindo que novos elementos sejam adicionados conforme a necessidade.

```text
[Paciente 1] → [Paciente 2] → [Paciente 3] → null
```

Cada nó mantém uma referência para o próximo elemento da fila.

Essa abordagem permite que a estrutura tenha capacidade flexível, limitada apenas pela memória disponível para a aplicação.

---

## 🔄 Funcionamento

O sistema permite simular os dois tipos de atendimento:

### Consultas Médicas

* Utiliza uma fila estática.
* Possui capacidade máxima de 5 agendamentos.
* O sistema deve impedir inserções quando a capacidade da fila estiver esgotada.
* Os pacientes são atendidos respeitando a ordem de chegada.

### Atendimento de Enfermagem

* Utiliza uma fila dinâmica.
* Não possui uma capacidade fixa previamente definida.
* Novos pacientes podem ser adicionados conforme a demanda.
* Os pacientes são atendidos respeitando a ordem de chegada.

---

## 📚 Objetivo do Projeto

O projeto foi desenvolvido com o objetivo de praticar a implementação de **estruturas de dados fundamentais em Java**, especialmente a diferença entre estruturas com capacidade previamente definida e estruturas que podem crescer dinamicamente.

Além da implementação das filas, o projeto demonstra conceitos de **TAD, POO, referências, nós encadeados e gerenciamento de capacidade**, utilizando apenas recursos nativos da linguagem Java.

---

## 👨‍💻 Autor

**Alexandre Roberto**

GitHub: [aleroberto](https://github.com/aleroberto)
