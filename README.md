# FitPlanner 🏋️

Aplicação web para gestão de treinos entre personal trainers e alunos. Professores cadastram treinos personalizados, alunos acompanham seus exercícios e IMC em um dashboard simples.

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#licença)

## ✨ Highlights

- 👥 **Dois perfis de usuário** — professor (trainer) e aluno (student), com permissões distintas
- 📋 **Cadastro de treinos** — professores montam treinos com séries, repetições e carga por exercício
- 📊 **Cálculo automático de IMC** — dashboard do aluno exibe IMC e classificação a partir de peso/altura
- 🔒 **Rotas protegidas** — acesso ao dashboard e treinos exige login
- 🎨 **UI responsiva** — construída com Tailwind CSS e ícones Lucide

## 🚀 Quick Start

```bash
git clone https://github.com/GuilhermeKaynam/FrontEnd-FitPlanner.git
cd FrontEnd-FitPlanner
npm install
npm run dev
```

Acesse `http://localhost:5173`, crie uma conta em **Registrar** e faça login para explorar o dashboard.

## 📦 Instalação detalhada

### Pré-requisitos
- [Node.js](https://nodejs.org/) 18+
- npm (instalado junto com o Node.js)

### Passo a passo
```bash
# 1. Clone o repositório
git clone https://github.com/GuilhermeKaynam/FrontEnd-FitPlanner.git

# 2. Entre na pasta do projeto
cd FrontEnd-FitPlanner

# 3. Instale as dependências
npm install

# 4. Rode o servidor de desenvolvimento
npm run dev
```

> Este projeto não requer variáveis de ambiente nem backend — os dados de usuários e treinos são mantidos em memória (estado do Zustand), sendo perdidos ao recarregar a página.

## 💻 Uso / Exemplos

### 1. Cadastro e login
Crie uma conta informando nome, email, senha e função (**Aluno** ou **Professor**). Alunos também informam altura e peso para o cálculo de IMC.

### 2. Como professor: cadastrar um treino
1. Acesse **Treinos**
2. Selecione um aluno já cadastrado
3. Adicione exercícios com nome, séries, repetições e carga
4. Envie o formulário — o treino fica disponível para o aluno

### 3. Como aluno: acompanhar treinos e IMC
- No **Dashboard**, veja seus dados de perfil e o IMC calculado automaticamente
- Em **Treinos**, visualize a lista de treinos cadastrados pelo professor

## 🗂️ Estrutura do projeto

```
FrontEnd-FitPlanner/
├── src/
│   ├── components/
│   │   ├── Layout.tsx          # Layout com navegação e proteção de rotas
│   │   ├── WorkoutForm.tsx     # Formulário de cadastro de exercícios
│   │   └── WorkoutList.tsx     # Listagem de treinos
│   ├── pages/
│   │   ├── Login.tsx           # Tela de login
│   │   ├── Register.tsx        # Tela de cadastro
│   │   ├── Dashboard.tsx       # Perfil do usuário + IMC
│   │   └── Workouts.tsx        # Cadastro e listagem de treinos
│   ├── store/
│   │   ├── useAuthStore.ts     # Estado global de autenticação (Zustand)
│   │   └── useWorkoutStore.ts  # Estado global de treinos (Zustand)
│   ├── types/
│   │   └── index.ts            # Tipos: User, Exercise, Workout
│   ├── utils/                  # Funções utilitárias (ex: cálculo de IMC)
│   ├── App.tsx                 # Definição de rotas
│   └── main.tsx                # Ponto de entrada da aplicação
├── index.html
├── package.json
├── tailwind.config.js
├── vite.config.ts
└── tsconfig.json
```

## 🛠️ Desenvolvimento

### Stack
- **React 18** + **TypeScript**
- **Vite** — build tool e dev server
- **React Router DOM** — roteamento e rotas protegidas
- **Zustand** — gerenciamento de estado global
- **Tailwind CSS** — estilização
- **Lucide React** — ícones
- **ESLint** — padronização de código

### Scripts disponíveis

| Comando | Descrição |
|---|---|
| `npm run dev` | Inicia o servidor de desenvolvimento |
| `npm run build` | Gera build de produção |
| `npm run preview` | Pré-visualiza o build de produção |
| `npm run lint` | Executa o ESLint no projeto |

## 🤝 Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. Faça commit das mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Envie para o seu fork (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## ❓ FAQ

**Os dados são salvos permanentemente?**
Não. Usuários e treinos ficam apenas em memória (estado do Zustand) e são perdidos ao recarregar a página, já que o projeto ainda não possui backend/persistência.

**Por que não consigo ver a tela de Treinos como aluno logo após cadastrar?**
O aluno só verá treinos depois que um professor cadastrar um treino vinculado a ele.

**Posso ter mais de um professor cadastrando treinos para o mesmo aluno?**
Sim, os treinos são vinculados por `studentId` e `trainerId`, então múltiplos professores podem cadastrar treinos para o mesmo aluno.

**A aplicação tem backend?**
Não nesta versão — é um front-end standalone. Integração com uma API é um próximo passo natural do projeto.

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar, modificar e distribuir.

---

Desenvolvido por [GuilhermeKaynam](https://github.com/GuilhermeKaynam)
