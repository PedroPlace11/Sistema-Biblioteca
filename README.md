# 📚 Biblioteca

Biblioteca é uma aplicação web desenvolvida em Laravel para gestão de livros, autores e editoras.  
O sistema permite organizar uma biblioteca digital, visualizar obras, autores e editoras, além de exportar dados para Excel.

A aplicação possui autenticação segura e interface moderna utilizando Tailwind CSS e DaisyUI.

---

## 📋 Funcionalidades

### Gestão de Livros

- **Criação de Livros**: Permite adicionar novos livros com ISBN, nome, editora, autores, bibliografia, preço e capa.
- **Consulta de Livros**: Exibe todos os livros cadastrados com capa, autores e editora.
- **Atualização de Livros**: Permite editar informações de um livro.
- **Eliminação de Livros**: Permite remover livros da base de dados.
- **Exportação para Excel**: Permite exportar a lista de livros para um ficheiro Excel.

### Gestão de Autores

- **Registo de Autores**: Permite criar novos autores com nome, fotografia e biografia.
- **Consulta de Autores**: Exibe autores cadastrados com foto e lista de livros escritos.
- **Atualização de Autores**: Permite editar os dados do autor.
- **Eliminação de Autores**: Permite remover autores da base de dados.

### Gestão de Editoras

- **Registo de Editoras**: Permite criar editoras com nome e logotipo.
- **Consulta de Editoras**: Exibe editoras cadastradas no sistema.
- **Atualização de Editoras**: Permite editar nome e logotipo.
- **Eliminação de Editoras**: Permite remover editoras do sistema.

### Visualização de Dados

- **Dashboard**: Apresenta estatísticas do sistema.
- **Página de Autor**: Mostra biografia e livros escritos pelo autor.
- **Página de Editora**: Exibe logotipo, livros publicados e autores.
- **Pesquisa e Ordenação**: Permite pesquisar livros por nome, autor ou editora.

---

## 🛠️ Tecnologias Utilizadas

- Laravel — Framework PHP utilizado para o backend da aplicação.
- Laravel Jetstream — Sistema de autenticação com login, registo e 2FA.
- Tailwind CSS — Framework CSS para estilização da interface.
- DaisyUI — Biblioteca de componentes UI baseada em Tailwind.
- Vite — Ferramenta para compilação de assets frontend.
- MySQL — Base de dados para armazenamento das informações.

---

## ⚙️ Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter instalado:

- PHP
- Composer
- Node.js
- NPM
- MySQL

---

### 1. Clone o repositório

```bash
git clone https://github.com/SEU-USUARIO/biblioteca.git  
cd biblioteca
```


---

### 2. Instale as dependências do Laravel

```bash
composer install
```

---

### 3. Instale as dependências do frontend
```bash
npm install
```

---

### 4. Configure o ambiente
```bash
cp .env.example .env  
php artisan key:generate
```

Configure a base de dados no arquivo `.env`.

---

### 5. Crie as tabelas da base de dados

```bash
php artisan migrate
```

---

### 6. Inserir dados iniciais

```bash
php artisan db:seed
```

---

### 7. Executar o frontend

```bash
npm run dev
```

---

### 8. Executar o servidor Laravel

```bash
php artisan serve
```

---

### 9. Acessar a aplicação

http://localhost:8000

---

## 📁 Estrutura do Projeto

```
📁 biblioteca/
├── 📁 app/
│   ├── 📁 Actions/                        # Ações do Fortify e Jetstream (autenticação)
│   ├── 📁 Exports/
│   │   └── 📄 LivrosExport.php            # Exportação de livros para Excel
│   ├── 📁 Http/
│   │   └── 📁 Controllers/                # Controladores das rotas da aplicação
│   │       ├── 📄 AutorController.php     # CRUD de autores
│   │       ├── 📄 DashboardController.php # Lógica do painel principal
│   │       ├── 📄 EditoraController.php   # CRUD de editoras
│   │       └── 📄 LivroController.php     # CRUD de livros
│   ├── 📁 Models/                         # Modelos Eloquent
│   │   ├── 📄 Autor.php                   # Modelo de autor
│   │   ├── 📄 Editora.php                 # Modelo de editora
│   │   ├── 📄 Livro.php                   # Modelo de livro
│   │   └── 📄 User.php                    # Modelo de utilizador
│   ├── 📁 Providers/                      # Provedores de serviço da aplicação
│   └── 📁 View/                           # Componentes de view personalizados
├── 📁 database/
│   ├── 📁 factories/                      # Fábricas para geração de dados de teste
│   ├── 📁 migrations/                     # Migrações do banco de dados
│   └── 📁 seeders/                        # Seeders para popular o banco de dados
├── 📁 resources/
│   └── 📁 views/
│       ├── 📁 autores/                    # Views do módulo de autores
│       │   ├── 📄 create.blade.php        # Formulário de criação de autor
│       │   ├── 📄 edit.blade.php          # Formulário de edição de autor
│       │   ├── 📄 index.blade.php         # Listagem de autores
│       │   └── 📄 show.blade.php          # Detalhe do autor
│       ├── 📁 editoras/                   # Views do módulo de editoras
│       │   ├── 📄 create.blade.php        # Formulário de criação de editora
│       │   ├── 📄 edit.blade.php          # Formulário de edição de editora
│       │   ├── 📄 index.blade.php         # Listagem de editoras
│       │   └── 📄 show.blade.php          # Detalhe da editora
│       ├── 📁 livros/                     # Views do módulo de livros
│       │   ├── 📄 create.blade.php        # Formulário de criação de livro
│       │   ├── 📄 edit.blade.php          # Formulário de edição de livro
│       │   ├── 📄 index.blade.php         # Listagem de livros
│       │   └── 📄 show.blade.php          # Detalhe do livro
│       ├── 📁 layouts/                    # Layouts base da aplicação
│       │   ├── 📄 app.blade.php           # Layout para utilizadores autenticados
│       │   └── 📄 guest.blade.php         # Layout para páginas públicas/guest
│       ├── 📄 dashboard.blade.php         # Painel principal com estatísticas e gráficos
│       ├── 📄 welcome.blade.php           # Página inicial pública
│       ├── 📄 policy.blade.php            # Página de política de privacidade
│       └── 📄 terms.blade.php             # Página de termos de serviço
├── 📁 routes/
│   ├── 📄 web.php                         # Rotas web da aplicação
│   ├── 📄 api.php                         # Rotas da API
│   └── 📄 console.php                     # Comandos Artisan personalizados
├── 📁 public/                             # Ficheiros públicos (imagens, build)
├── 📁 storage/                            # Armazenamento de ficheiros e logs
├── 📄 artisan                             # CLI do Laravel
├── 📄 composer.json                       # Dependências PHP
└── 📄 package.json                        # Dependências JavaScript
```
