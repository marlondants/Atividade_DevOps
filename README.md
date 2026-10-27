# Atividade DevOps: Login e Cadastro

Projeto da disciplina **Cultura DevOps**. É um sistema simples de login e cadastro, feito só com HTML e CSS, criado para praticar controle de versão com Git e GitHub, o fluxo de branches Gitflow e uma pipeline de integração contínua com GitHub Actions.

## Páginas do projeto

| Arquivo | O que é |
|---|---|
| `index.html` | Tela de login |
| `cadastro.html` | Tela de criação de conta |
| `painel_login.html` | Tela exibida depois do login |
| `style.css` | Estilos compartilhados pelas páginas |

Os formulários validam os campos no próprio navegador: campos obrigatórios, e-mail em formato válido e senha com no mínimo 6 caracteres. O projeto não possui servidor nem banco de dados, então o login apenas simula a navegação entre as telas.

## Pré-requisitos

- Um navegador atualizado (Chrome, Firefox ou Edge)
- [Git](https://git-scm.com/) instalado
- [Visual Studio Code](https://code.visualstudio.com/) (recomendado)

## Como rodar

1. Clone o repositório:

```bash
git clone https://github.com/marlondants/Atividade_DevOps.git
```

2. Entre na pasta do projeto:

```bash
cd Atividade_DevOps
```

3. Abra o arquivo `index.html` no navegador (duplo clique no arquivo).

## Fluxo de trabalho (Gitflow)

O projeto segue o modelo de branches do Gitflow:

| Branch | Função |
|---|---|
| `main` | Código estável, nunca recebe commit direto |
| `develop` | Integração das funcionalidades antes de ir para a `main` |
| `feature/*` | Uma branch para cada nova funcionalidade |
| `bugfix/*` | Correção de erros comuns |

Caminho de uma alteração: `feature/*` → Pull Request → `develop` → Pull Request → `main`.

As mensagens de commit seguem o padrão **Conventional Commits**, por exemplo `feat: adiciona tela de cadastro`, `fix: corrige link do painel` e `docs: atualiza README`.

## Pipeline (GitHub Actions)

A pipeline fica em `.github/workflows/pipeline.yaml` e roda a cada push e a cada Pull Request. Ela é dividida em quatro etapas, executadas em sequência:

1. **Preparação:** confere se os arquivos obrigatórios existem e não estão vazios.
2. **Validação de links:** verifica se links, estilos e destinos dos formulários apontam para arquivos existentes.
3. **Testes dos formulários:** confere a estrutura do login, do cadastro e do painel.
4. **Publicação no GitHub Pages:** publica o site, somente quando o código chega na `main`.

Se uma etapa falha, as seguintes não são executadas.

## Estrutura do repositório

```
.
├── .github/
│   └── workflows/
│       └── pipeline.yaml
├── cadastro.html
├── index.html
├── painel_login.html
├── style.css
└── README.md
```

## Autor

Marlon Dantas, estudante de Ciências da Computação.
