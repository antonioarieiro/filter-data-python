# Boas vindas ao repositório do projeto Job Filter!

## Sumário

- [Sumário](#sumário)
- [Habilidades](#habilidades)
- [Entregáveis](#entregáveis)
  - [O que foi desenvolvido](#o-que-foi-desenvolvido)
  - [Estrutura](#estrutura)
    - [Linter](#linter)
    - [Testes](#testes)
  - [Requisitos](#requisitos)
    - [Requisitos obrigatórios](#requisitos-obrigatórios)
      - [1 - Implemente a função `read`](#1---implemente-a-função-read)
      - [2 - Implemente a função `get_unique_job_types`](#2---implemente-a-função-get_unique_job_types)
      - [3 - Implemente a função `get_unique_industries`](#3---implemente-a-função-get_unique_industries)
      - [4 - Implemente a função `get_max_salary`](#4---implemente-a-função-get_max_salary)
      - [5 - Implemente a função `get_min_salary`](#5---implemente-a-função-get_min_salary)
      - [6 - Implemente a função `filter_by_job_type`](#6---implemente-a-função-filter_by_job_type)
      - [7 - Implemente a função `filter_by_industry`](#7---implemente-a-função-filter_by_industry)
      - [8 - Implemente a função `matches_salary_range`](#8---implemente-a-função-matches_salary_range)
      - [9 - Implemente a função `filter_by_salary_range`](#9---implemente-a-função-filter_by_salary_range)
      - [10 - Implemente um teste para a função `sort_by`](#10---implemente-um-teste-para-a-função-sort_by)
    - [Requisitos bônus](#requisitos-bônus)
      - [11 - Implemente a página de um job](#11---implemente-a-página-de-um-job)
  - [Depois de terminar o desenvolvimento](#depois-de-terminar-o-desenvolvimento)
    - [Revisando um pull request](#revisando-um-pull-request)
- [Avisos Finais](#avisos-finais)

---

## Habilidades

- Utilizar o terminal interativo do Python.
- Utilizar estruturas condicionais e de repetição.
- Utilizar funções built-in do Python.
- Utilizar tratamento de exceções.
- Realizar a manipulação de arquivos.
- Escrever funções.
- Escrever testes com Pytest.
- Escrever seus próprios módulos e importá-los em outros códigos.

-

### O que foi desenvolvido

análises a partir de um conjunto de dados sobre empregos. Suas implementações serão incorporadas a um aplicativo Web desenvolvido com Flask (um framework web muito popular na comunidade Python). Você também terá a oportunidade de escrever testes para a implementação de uma análise de dados. Por fim, como bônus, você terá o desafio de escrever uma rota e view para um recurso novo usando Flask!

Os dados foram extraídos do site [Glassdoor](https://www.glassdoor.com.br/) e obtidos através do [Kaggle](https://www.kaggle.com/atharvap329/glassdoor-data-science-job-data), uma plataforma disponiblizando conjuntos de dados para cientistas de dados.

---

### Estrutura

Este repositório já contém um _template_ com a estrutura de diretórios e arquivos:

```
.
├── README.md
├── dev-requirements.txt
├── feedback.jsonc
├── requirements.txt
├── src
│   ├── app.py
│   ├── insights.py
│   ├── jobs.csv
│   ├── jobs.py
│   ├── more_insights.py
│   ├── routes_and_views.py
│   ├── sorting.py
│   └── templates
│       ├── base.jinja2
│       ├── includes
│       │   └── nav.jinja2
│       ├── index.jinja2
│       ├── job.jinja2
│       └── list_jobs.jinja2
├── tests
│   ├── __init__.py
│   ├── mocks
│   │   ├── job_1.html
│   │   ├── jobs.csv
│   │   ├── jobs_with_industries.csv
│   │   ├── jobs_with_salaries.csv
│   │   └── jobs_with_types.csv
│   ├── sorting
│   │   ├── conftest.py
│   │   ├── mocks.py
│   │   └── test_sorting.py
│   ├── test_feedback.py
│   ├── test_flask_app.py
│   ├── test_insights.py
│   ├── test_jobs.py
│   ├── test_more_insights.py
│   └── test_routes_and_views.py
```



### Como iniciar

1. Clone o repositório

- `git clone https://github.com/tryber/sd-010-b-project-job-insights.git`.
- Entre na pasta do repositório que você acabou de clonar:
  - `cd sd-010-b-project-job-insights`

2. Crie o ambiente virtual para o projeto

- `python3 -m venv .venv && source .venv/bin/activate`

3. Instale as dependências

- `python3 -m pip install -r dev-requirements.txt`



#### Testes

Para executar os testes certifique-se de que os seguintes passos foram realizados;

1. **criar o ambiente virtual**

```bash
$ python3 -m venv .venv
```

2. **ativar o ambiente virtual**

```bash
$ source .venv/bin/activate
```

3. **instalar as dependências no ambiente virtual**

```bash
$ python3 -m pip install -r dev-requirements.txt
```

Com o seu ambiente virtual ativo, as dependências serão instaladas neste ambiente.
Quando precisar desativar o ambiente virtual, execute o comando "deactivate". Lembre-se de ativar novamente quando voltar a trabalhar no projeto.

O arquivo `dev-requirements.txt` contém todas as dependências que serão utilizadas no projeto, ele está agindo como se fosse um `package.json` de um projeto `Node.js`.

Com esta preparação feita, podemos executar os testes:

**Executar os testes**

```bash
$ python3 -m pytest
```

O arquivo `pyproject.toml` já configura corretamente o pytest. Entretanto, caso você tenha problemas com isso queira explicitamente uma saída completa, o comando é:

```bash
python3 -m pytest -s -vv
```

Caso precise executar apenas um arquivo de testes basta executar o comando:

```bash
python3 -m pytest tests/nomedoarquivo.py
```

Caso precise executar apenas uma função de testes basta executar o comando:

```bash
python3 -m pytest -k nome_da_func_de_tests
```

Se quiser saber mais sobre a instalação de dependências com `pip`, veja esse [artigo](https://medium.com/python-pandemonium/better-python-dependency-and-package-management-b5d8ea29dff1).

Além dos testes com o Pytest, você pode (e vai ser bem bacana) rodar a aplicação flask para visualizar no navegador o resultado do desenvolvimento das funções.
Para isso, digite o comando `flask run`, e acesse o site gerado pelo Flask em `http://localhost:5000`. No começo do desenvolvimento, você verá que muitas coisas não funcionam, mas conforme você for implementando os requisitos, perceberá que a aplicação web começa a utilizar suas implementações e passa a ganhar vida.

---

