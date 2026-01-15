# 🏨 Projeto 5 — Sistema de Reservas (Rails + MVC)

## 🎯 Objetivo

Criar um sistema onde usuários possam reservar horários (ex: sala, consulta médica ou restaurante), evitando conflitos de datas.

---

## 📌 Escopo do Projeto (MVP)

### Funcionalidades

- Criar reservas
- Listar reservas
- Ver detalhes de uma reserva
- Evitar reservas em horários já ocupados
- Cancelar reserva

---

## 🧱 Estrutura MVC

### 📦 Models

- Usuario
- Reserva
- Sala (ou Médico / Mesa / Recurso)

---

### 🧠 Regras de Negócio (Model)

- Uma sala não pode ter duas reservas no mesmo horário
- A data da reserva não pode ser no passado
- A reserva pertence a um usuário e a uma sala

---

### 🎮 Controllers

- ReservasController
- SalasController
- UsuariosController

> Controllers devem ser simples, sem regras de negócio pesadas.

---

### 🎨 Views

- `reservas/index` → lista de reservas
- `reservas/new` → formulário de nova reserva
- `reservas/show` → detalhes da reserva
- `salas/index` → lista de salas

---

## 🗄️ Modelagem do Banco de Dados

### Usuario

| Campo | Tipo   |
|------|--------|
| nome | string |
| email | string |
| senha | hash  |

---

### Sala

| Campo | Tipo    |
|------|---------|
| nome | string  |
| capacidade | integer |

---

### Reserva

| Campo | Tipo |
|------|------|
| usuario_id | references |
| sala_id | references |
| data_inicio | datetime |
| data_fim | datetime |

---

## 📌 Observações

- O sistema deve impedir conflitos de horário no momento da criação da reserva
- As validações devem ficar concentradas no **Model**
- O projeto segue o padrão **MVC do Ruby on Rails**
