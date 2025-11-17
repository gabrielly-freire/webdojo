# Cypress — Guia básico

## Pré-requisitos

* Node.js instalado na máquina (instalar um versão do cypress compatível com o seu nodejs)

## Passo a passo para iniciar um projeto com Cypress

### 1. Criar ou selecionar um diretório
Escolha onde seu projeto ficará.
### 2. Criar um novo projeto Node.js
```bash
npm init -y
```
### 3. Instalar o Cypress como dependência de desenvolvimento
```bash
npm install cypress --save-dev
```
### 4. Abrir o Cypress pela primeira vez
```bash
npx cypress open
```
### Estrutura gerada no projeto
```text
seu-projeto/
├── cypress/
│   ├── e2e/                 # Arquivos de testes end-to-end
│   ├── fixtures/            # Dados mock para testes
│   ├── support/
│   │   ├── commands.js      # Comandos customizados
│   │   └── e2e.js           # Configurações globais
├── cypress.config.js        # Configuração principal do Cypress
└── package.json
```
### 5. Selecionar a opção "E2E Testing"
### 6. Continuar
### 7. Escolher o navegador Electron

# Estrutura básica de um teste

```js
describe('Nome da funcionalidade', () => {
  it('deve realizar a ação X', () => {
    cy.visit('https://minha-aplicacao.com');

    // ações...
  });

  it('deve realizar a ação Y', () => {
    cy.visit('https://minha-aplicacao.com');

    // ações...
  });

});
```

# Ações comuns no Cypress

```js
cy.get('seletor').type('texto');        // Digitar
cy.get('seletor').click();              // Clicar
cy.get('seletor').check();              // Marcar checkbox / radio
cy.get('seletor').select('valor');      // Selecionar opção de <select>
cy.contains('Nome do botão').click();   // Buscar elemento pelo texto
```

## Seletores úteis

### Por ID
```js
cy.get('#idDoElemento');
```

### Por classe
```js
cy.get('.nome-da-classe');
```

### Por atributo
```js
cy.get('input[placeholder="Digite seu nome"]');
cy.get('[data-testid="btn-enviar"]'); // recomendado
```

### Por texto
```js
cy.contains('Enviar').click();
```

## Asserções

### Verificar visibilidade
```js
cy.get('#mensagem').should('be.visible');
```

### Verificar se contém texto
```js
cy.get('.alert').should('contain', 'Sucesso');
```

### Verificar valor de um input
```js
cy.get('#nome').should('have.value', 'Gabrielly');
```

### Verificar classe adicionada ou removida
```js
cy.get('#btn').should('have.class', 'ativo');
```

### Verificar quantidade de elementos
```js
cy.get('.card').should('have.length', 3);
```

### Verificar URL
```js
cy.url().should('include', '/dashboard');
```

### Verificar atributo
```js
cy.get('img').should('have.attr', 'src', '/assets/logo.png');
```
