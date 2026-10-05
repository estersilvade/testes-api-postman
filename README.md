# 🧪 Testes de API com Postman + Newman + GitHub Actions

![Testes de API](https://github.com/estersilvade/testes-api-postman/actions/workflows/testes-api.yml/badge.svg)

Projeto de automação de testes de API da [ServeRest](https://serverest.dev), uma API pública que simula uma loja virtual.

Os testes rodam sozinhos no **GitHub Actions** a cada mudança no código e todo dia útil de manhã.

## 🎯 O que é testado

| ID | Cenário | Tipo |
|----|---------|------|
| CT01 | Cadastrar usuário administrador | ✅ Positivo |
| CT02 | Não cadastrar usuário com e-mail repetido | ❌ Negativo |
| CT03 | Buscar usuário por ID (com validação de contrato) | ✅ Positivo |
| CT04 | Listar usuários | ✅ Positivo |
| CT05 | Buscar usuário inexistente | ❌ Negativo |
| CT06 | Login com sucesso (gera token) | ✅ Positivo |
| CT07 | Login com senha inválida | ❌ Negativo |
| CT08 | Cadastrar produto com token | ✅ Positivo |
| CT09 | Não cadastrar produto sem token | ❌ Negativo |
| CT10 | Buscar produto por ID | ✅ Positivo |
| CT11 | Excluir produto | ✅ Positivo |
| CT12 | Excluir usuário (limpeza dos dados) | ✅ Positivo |

**12 cenários · 28 validações**

## 🛠️ Boas práticas aplicadas

- **Dados dinâmicos:** cada execução cria um usuário novo. Os testes não dependem de dados fixos.
- **Encadeamento:** o ID e o token de uma requisição são usados nas seguintes.
- **Limpeza:** os dados criados são excluídos no final.
- **Cenários negativos:** valida status e mensagens de erro.
- **Contrato:** confere os campos retornados pela API.
- **Performance básica:** tempo de resposta abaixo de 2 segundos.
- **Relatório HTML:** gerado a cada execução e salvo no GitHub Actions.

## ▶️ Como rodar no seu computador

Pré-requisito: [Node.js](https://nodejs.org) instalado.

```bash
npm install
npm test
```

Para gerar o relatório HTML em `reports/relatorio.html`:

```bash
npm run test:report
```

Você também pode importar `collections/serverest.postman_collection.json` no Postman e rodar pelo **Collection Runner**.

## 📁 Estrutura

```
collections/   → collection do Postman com os testes
.github/       → pipeline do GitHub Actions
package.json   → scripts do Newman
```

## 🤖 Desenvolvido com apoio de IA

Projeto criado com apoio do **Claude** (Anthropic), conectado diretamente ao Postman e ao GitHub.

## 👩‍💻 Autora

**Ester Silva de Souza** — QA Engineer
