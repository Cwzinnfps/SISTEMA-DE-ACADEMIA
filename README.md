# 🏋️ Sistema de Gestão de Academia Universitária

## 📖 Sobre o Projeto

Este projeto consiste no desenvolvimento de um **Sistema de Gestão de Academia Universitária**, capaz de administrar associados, planos, aulas coletivas e pagamentos de uma academia situada no campus universitário.

O sistema foi desenvolvido como parte do **Projeto Semestral da disciplina de Engenharia de Software**, do curso de **Engenharia de Software do Centro Universitário Tiradentes de Pernambuco (UNIT-PE)**.

A aplicação foi implementada em **Python**, utilizando **Programação estruturada em funções** e persistência de dados em arquivo **JSON**, permitindo o armazenamento das informações de associados, aulas e pagamentos entre execuções do sistema.

---

## 🎯 Objetivo

O principal objetivo do sistema é automatizar o processo de gestão de uma academia universitária, garantindo:

- Cadastro e controle de associados;
- Gerenciamento dos diferentes tipos de planos (mensal, semestral, anual e estudante);
- Agendamento e cancelamento de aulas coletivas;
- Controle de pagamentos e mensalidades;
- Cálculo automático de vencimento dos planos;
- Histórico financeiro de cada associado.

---

## 👥 Atores do Sistema

O sistema foi desenvolvido considerando os seguintes tipos de usuários:

### Associado
Estudante ou servidor cadastrado na academia, com um plano ativo, que pode agendar aulas coletivas.

### Recepcionista
Responsável por cadastrar associados, registrar pagamentos e gerenciar agendamentos.

### Instrutor
Responsável pelas aulas coletivas oferecidas (musculação livre, funcional, yoga, spinning e natação).

---

## ⚙️ Funcionalidades Implementadas

### Gestão de Associados
O sistema permite:
- Cadastrar novos associados com nome, CPF e plano;
- Listar todos os associados cadastrados;
- Calcular automaticamente a data de vencimento do plano.

---

### Gestão de Planos

Cada associado escolhe um dos quatro planos disponíveis:

| Plano | Valor | Duração |
|---|---|---|
| Mensal | R$ 120,00 | 1 mês |
| Semestral | R$ 600,00 | 6 meses |
| Anual | R$ 1.000,00 | 12 meses |
| Estudante | R$ 350,00 | 6 meses |

---

### Agendamento de Aulas Coletivas

O sistema permite agendar aulas nas seguintes modalidades:

- Musculação Livre;
- Funcional;
- Yoga;
- Spinning;
- Natação.

Cada agendamento registra associado, modalidade, data, hora e status (confirmado/cancelado).

**Exemplo:**

```
Associado: João Silva (ID 1)
Modalidade: Yoga
Data: 25/06/2026
Hora: 08:00
```

**Resultado:** Aula agendada com status "confirmado".

---

### Cancelamento de Aulas

O associado pode cancelar uma aula já agendada. O sistema localiza os agendamentos ativos daquele associado e altera o status para "cancelado".

---

### Controle de Pagamentos

Durante o cadastro e a manutenção do plano, o sistema registra automaticamente:

- Pagamento de adesão ao plano;
- Pagamentos manuais (mensalidades);
- Descrição e valor de cada lançamento.

Essas informações ficam disponíveis no extrato financeiro do associado.

---

### Extrato Financeiro

O sistema permite consultar o histórico de pagamentos por associado ou de todos os associados.

**Exemplo:**

Associado: 1

**Resultado:**
- Lista de todos os pagamentos com data, descrição e valor;
- Valor total pago pelo associado.

---

## 🗄️ Armazenamento de Dados

O projeto utiliza um arquivo **JSON** (`dados.json`) como base de persistência, funcionando de forma similar a um banco de dados local, sem necessidade de servidor.

### "Tabela": associados

Responsável por armazenar os dados dos membros cadastrados.

| Campo | Tipo |
|---|---|
| id (chave) | STRING |
| nome | STRING |
| cpf | STRING |
| plano | STRING |
| vencimento | DATE |

---

### "Tabela": aulas

Responsável por armazenar os agendamentos de aulas coletivas.

| Campo | Tipo |
|---|---|
| id_associado | STRING |
| nome | STRING |
| modalidade | STRING |
| data | DATE |
| hora | TIME |
| status | STRING |

---

### "Tabela": pagamentos

Responsável por armazenar os lançamentos financeiros.

| Campo | Tipo |
|---|---|
| id | STRING |
| data | DATE |
| desc | STRING |
| valor | FLOAT |

---

### Controle interno

| Campo | Tipo |
|---|---|
| proximo_id | INT |

---

## 💻 Tecnologias Utilizadas

- Python 3
- Módulo `json` (persistência de dados)
- Módulo `os` (verificação de arquivos)
- Módulo `datetime` (cálculo de datas e vencimentos)
- Programação estruturada em funções

---

## 🚀 Como Executar

### 1. Pré-requisitos

Ter o **Python 3.6 ou superior** instalado. Não é necessário instalar nenhuma biblioteca externa.

### 2. Clonar o repositório

```
git clone https://github.com/seu-usuario/academia-unit.git
cd academia-unit
```

### 3. Executar o sistema

```
python academia_simples.py
```

### 4. Primeira execução

Na primeira vez que o sistema for executado, o arquivo `dados.json` será criado automaticamente na mesma pasta, já estruturado para armazenar associados, aulas e pagamentos.

---

## 📚 Conceitos Aplicados

Durante o desenvolvimento foram utilizados conceitos importantes da Engenharia de Software e Programação:

- Programação estruturada e modularização em funções;
- Persistência de dados em arquivo;
- Manipulação de datas;
- Estruturas condicionais;
- Estruturas de repetição;
- Tratamento de entrada do usuário;
- CRUD (Create, Read, Update e Delete) aplicado a associados, aulas e pagamentos.

---

## 📌 Considerações Finais

O Sistema de Gestão de Academia Universitária foi desenvolvido com o objetivo de simular um ambiente real de administração de uma academia, permitindo o controle de associados, planos, aulas coletivas e pagamentos de forma simples e funcional.

O projeto demonstra a aplicação prática dos conceitos estudados ao longo da disciplina, integrando lógica de programação, persistência de dados e organização modular do código em uma solução funcional.

---

**Centro Universitário Tiradentes de Pernambuco — Engenharia de Software — 2026.1**
**Prof. Dr. David Barrientos**
