readme

# Sistema de Agendamento - BarberFlow
Projeto Integrador Transdisciplinar em Engenharia de Software II

## 1. Escopo e Objetivo
O **BarberFlow** é uma aplicação web desenvolvida para automatizar e organizar o agendamento de horários em barbearias de pequeno e médio porte. O sistema elimina o controle manual em papel, reduz conflitos de horários e facilita a visualização dos serviços prestados.

## 2. Requisitos Funcionais (RF)
- **RF01:** O sistema deve permitir o cadastro de clientes (nome e telefone).
- **RF02:** O sistema deve listar os serviços disponíveis (Corte, Barba, Completo) e seus respectivos valores.
- **RF03:** O sistema deve permitir a realização de agendamentos vinculando um cliente, um serviço, data e horário.
- **RF04:** O sistema deve exibir a lista de agendamentos realizados e permitir o cancelamento/exclusão.

## 3. Arquitetura e Tecnologias
- **Padrão Arquitetural:** MVC (Model-View-Controller).
- **Front-end (View):** HTML5, CSS3 e JavaScript puro (foco em usabilidade e interface limpa).
- **Back-end / Controller:** JavaScript (Node.js/LocalStorage para prototipação rápida) ou Python (Flask).
- **Banco de Dados:** Relacional (MySQL / SQLite).

## 4. Dicionário de Dados

### Tabela: `clientes`
| Campo | Tipo | Restrição | Descrição |
| :--- | :--- | :--- | :--- |
| `id` | INT | PK, AUTO_INCREMENT | Identificador único do cliente |
| `nome` | VARCHAR(100) | NOT NULL | Nome completo do cliente |
| `telefone` | VARCHAR(20) | NOT NULL | Telefone/WhatsApp para contato |

### Tabela: `servicos`
| Campo | Tipo | Restrição | Descrição |
| :--- | :--- | :--- | :--- |
| `id` | INT | PK, AUTO_INCREMENT | Identificador único do serviço |
| `descricao` | VARCHAR(100) | NOT NULL | Nome do serviço (ex: Corte Social) |
| `valor` | DECIMAL(10,2) | NOT NULL | Preço do serviço em reais |

### Tabela: `agendamentos`
| Campo | Tipo | Restrição | Descrição |
| :--- | :--- | :--- | :--- |
| `id` | INT | PK, AUTO_INCREMENT | Identificador único do agendamento |
| `cliente_id` | INT | FK (`clientes.id`) | Chave estrangeira do cliente |
| `servico_id` | INT | FK (`servicos.id`) | Chave estrangeira do serviço |
| `data_hora` | DATETIME | NOT NULL | Data e hora marcadas |