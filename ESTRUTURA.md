# 📁 Estrutura do Blog

## 🗂️ Organização

```
log-do-garras/
├── _pages/                     # 📂 Páginas principais (organizadas)
│   ├── index.md                # Página Início
│   ├── projetos.md             # Página Projetos
│   ├── sobre.md                # Página Sobre
│   └── contato.md              # Página Contato
├── projetos/                   # 📂 Pasta com todos os projetos
│   ├── ecommerce/              # Projeto 1 (subpasta)
│   │   ├── index.md            # Página principal do projeto
│   │   ├── visao-geral.md      # Navbar específica do E-commerce
│   │   ├── tecnologias.md      # Navbar específica do E-commerce
│   │   ├── funcionalidades.md  # Navbar específica do E-commerce
│   │   └── deploy.md           # Navbar específica do E-commerce
│   ├── blog/                   # Projeto 2 (subpasta)
│   │   ├── index.md
│   │   ├── introducao.md       # Navbar específica do Blog
│   │   ├── arquitetura.md      # Navbar específica do Blog
│   │   └── editor.md           # Navbar específica do Blog
│   └── api/                    # Projeto 3 (subpasta)
│       ├── index.md
│       ├── overview.md         # Navbar específica da API
│       ├── endpoints.md        # Navbar específica da API
│       ├── autenticacao.md     # Navbar específica da API
│       └── exemplos.md         # Navbar específica da API
├── _config.yml                 # Configuração do Jekyll
├── _site/                      # ⚠️ Gerada automaticamente (no .gitignore)
├── .jekyll-cache/              # ⚠️ Cache do Jekyll (no .gitignore)
└── .gitignore                  # Ignora _site e cache
```

## ⚠️ Pastas que NÃO devem ser versionadas

- `_site/` - Gerada automaticamente pelo Jekyll ao buildar
- `.jekyll-cache/` - Cache do Jekyll

**Essas pastas já estão no `.gitignore`**

## 🎯 Navegação Resultante

### Navbar Principal (todas as páginas)
```
📄 Início
📁 Projetos
📄 Sobre
📄 Contato
```

### Quando entrar em E-commerce
```
📄 Início
📁 Projetos
  📁 E-commerce           ← Você está aqui
    📄 Visão Geral        ← Navbar específica do projeto
    📄 Tecnologias
    📄 Funcionalidades
    📄 Deploy
  📁 Blog Platform
  📁 API REST
📄 Sobre
📄 Contato
```

### Quando entrar em Blog Platform
```
📄 Início
📁 Projetos
  📁 E-commerce
  📁 Blog Platform        ← Você está aqui
    📄 Introdução         ← Navbar específica diferente!
    📄 Arquitetura
    📄 Editor
  📁 API REST
📄 Sobre
📄 Contato
```

### Quando entrar em API REST
```
📄 Início
📁 Projetos
  📁 E-commerce
  📁 Blog Platform
  📁 API REST             ← Você está aqui
    📄 Overview           ← Navbar específica diferente!
    📄 Endpoints
    📄 Autenticação
    📄 Exemplos
📄 Sobre
📄 Contato
```

## ✅ Como Funciona

### Cada projeto tem:
1. **Subpasta própria** em `projetos/nome-projeto/`
2. **index.md** com `has_children: true`
3. **Páginas específicas** com navbar própria

### Front Matter do projeto (index.md):
```yaml
---
title: Nome do Projeto
parent: Projetos
has_children: true          # Habilita subpáginas
permalink: /projetos/nome/
---
```

### Front Matter das páginas do projeto:
```yaml
---
title: Nome da Página
parent: Nome do Projeto     # Mesmo "title" do index.md
grand_parent: Projetos
nav_order: 1
---
```

## 🚀 Adicionar Novo Projeto

1. Criar subpasta:
```bash
mkdir projetos/novo-projeto
```

2. Criar index.md:
```yaml
---
title: Novo Projeto
parent: Projetos
has_children: true
nav_order: 4
permalink: /projetos/novo-projeto/
---

# Novo Projeto
Descrição...
```

3. Criar páginas específicas:
```yaml
---
title: Tópico 1
parent: Novo Projeto
grand_parent: Projetos
nav_order: 1
---

Conteúdo...
```

## ⚙️ Executar

```bash
bundle exec jekyll serve
```

Acesse: http://localhost:4000
