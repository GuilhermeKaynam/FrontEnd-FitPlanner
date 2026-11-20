# FitPlanner — Front-end

Aplicação web para gestão de treinos entre personal trainers e alunos. O professor monta treinos com séries, repetições e carga; o aluno acompanha seus treinos e vê o IMC calculado no próprio dashboard.

## Objetivo

Prototipar a experiência do FitPlanner do ponto de vista dos dois perfis de usuário — professor e aluno — com estado global, rotas protegidas e regras de permissão no front-end.

> Esta versão é independente: os dados ficam em memória (Zustand) e são perdidos ao recarregar a página. A API correspondente está em [BackEnd-FitPlanner](https://github.com/GuilhermeKaynam/BackEnd-FitPlanner); a integração entre os dois é um próximo passo.

## Funcionalidades

- **Cadastro com perfil**: aluno (com altura e peso) ou professor.
- **Login e rotas protegidas**: dashboard e treinos exigem usuário autenticado.
- **Dashboard do aluno** com dados do perfil, IMC e classificação.
- **Cadastro de treinos (professor)**: seleciona o aluno e adiciona exercícios com nome, séries, repetições e carga.
- **Listagem de treinos** para o aluno, filtrada pelos treinos atribuídos a ele.

## Tecnologias

- React 18 + TypeScript
- Vite
- React Router DOM
- Zustand (estado global)
- Tailwind CSS
- Lucide React

## Arquitetura

| Pasta | Responsabilidade |
|---|---|
| `src/store` | `useAuthStore` (usuários e sessão) e `useWorkoutStore` (treinos) |
| `src/pages` | `Login`, `Register`, `Dashboard`, `Workouts` |
| `src/components` | `Layout` (navegação e proteção de rotas), `WorkoutForm`, `WorkoutList` |
| `src/utils/imc.ts` | Cálculo do IMC e classificação |
| `src/types` | Tipos `User`, `Exercise`, `Workout` |

## Estrutura de diretórios

```
FrontEnd-FitPlanner/
└── src/
    ├── components/   # Layout, WorkoutForm, WorkoutList
    ├── pages/        # Login, Register, Dashboard, Workouts
    ├── store/        # Zustand
    ├── types/
    ├── utils/        # imc.ts
    ├── App.tsx       # rotas
    └── main.tsx
```

## Como executar localmente

Pré-requisito: Node.js 18+.

```bash
git clone https://github.com/GuilhermeKaynam/FrontEnd-FitPlanner.git
cd FrontEnd-FitPlanner
npm install
npm run dev
```

Acesse `http://localhost:5173`, crie uma conta de professor e outra de aluno para testar os dois fluxos. Não há variáveis de ambiente.

## Melhorias futuras

- Consumir a API do [BackEnd-FitPlanner](https://github.com/GuilhermeKaynam/BackEnd-FitPlanner) com autenticação JWT.
- Persistir a sessão entre recarregamentos.
- Edição e exclusão de treinos.
