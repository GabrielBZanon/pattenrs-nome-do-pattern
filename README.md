# Design-Patterns
Padrões Arquiteturais

#Definição
O Factory Pattern é um padrão de criação que centraliza e abstrai a criação de objetos, permitindo que o código cliente solicite um objeto com base em um parâmetro simples, sem saber como ele é criado internamente.

Ele reduz o acoplamento, facilita a manutenção e torna o código mais flexível e reutilizável, especialmente quando há múltiplos tipos de objetos a serem instanciados de forma padronizada.


# Exemplo de Factory Pattern em JavaScript

Este projeto demonstra como utilizar o **Factory Pattern (Padrão de Fábrica)** em JavaScript para criar objetos de forma organizada, flexível e reutilizável.

---

## Objetivo

O objetivo é mostrar como aplicar o **Design Pattern de Criação** chamado `Factory` para centralizar a criação de objetos, tornando o código mais limpo e fácil de manter.

---

## Estrutura do Projeto

```
/src
 ├── classes/
 │    ├── Livro.js
 │    ├── Smartphone.js
 │    ├── Tablet.js
 ├── factory/
 │    └── ProdutoFactory.js
 └── app.js
```

---

## O que é o Factory Pattern?

O **Factory Pattern** é um padrão de projeto que fornece uma **interface para criar objetos em uma superclasse**, mas **permite que as subclasses decidam qual classe instanciar**.

> 💡 Exemplo lúdico: Pense em uma fábrica de pizzas: você escolhe o sabor, e a fábrica sabe como montar e entregar. Você não precisa saber como fazer a massa, molho, etc.
> 💡 Exemplo real: Você faz um pedido de "livro" e a fábrica cria um objeto do tipo `Livro` automaticamente, sem você precisar saber como isso é feito.

---

## Produtos Criados

O projeto trabalha com os seguintes produtos:

- **📘 Livro**
- **📱 Smartphone**
- **💻 Tablet**

Cada um é representado por sua própria classe e possui nome e preço definidos.

---

## Como funciona?

### 1. Criamos classes separadas para cada produto:

```js
// Livro.js
class Livro {
    constructor() {
        this.nome = 'Livro de Programação';
        this.preco = 39.90;
    }
}
```

### 2. Criamos a `ProdutoFactory`:

```js
class ProdutoFactory {
    criar(tipo) {
        switch (tipo) {
            case 'livro': return new Livro();
            case 'smartphone': return new Smartphone();
            case 'tablet': return new Tablet();
            default: throw new Error('Tipo inválido');
        }
    }
}
```

### 3. No `app.js`, usamos a fábrica:

```js
const factory = new ProdutoFactory();

const livro = factory.criar('livro');
console.log(livro);
```

---

## ✅ Benefícios do Factory Pattern

| **Benefício**                          | **Descrição**                                                           |
|----------------------------------------|-------------------------------------------------------------------------|
| Reutilização de código              | A lógica de criação pode ser reaproveitada em vários lugares            |
| Código mais limpo e organizado      | Reduz o acoplamento e melhora a legibilidade do sistema                 |
| Encapsulamento da lógica de criação| A criação dos objetos é centralizada, sem expor detalhes ao cliente     |
| Facilidade para adicionar novos tipos| Novas classes podem ser adicionadas sem modificar o código existente    |


## ❌ Desvantagens do Factory Pattern

| **Desvantagem**                        | **Explicação**                                                            |
|---------------------------------------|---------------------------------------------------------------------------|
| Aumento de classes                    | Pode gerar muitas fábricas e subclasses                                  |
| Lógica de decisão complexa            | Muitos `if` ou `switch` dificultam a leitura                             |
| Menos controle na personalização      | O objeto vem pronto, com pouca flexibilidade de configuração             |
| Pode ser exagerado para objetos simples| Às vezes, usar `new Classe()` direto seria mais simples                   |

---

## 🔄 Comparação: Factory Pattern vs Builder Pattern

| **Característica**     | **Factory Pattern**                                     | **Builder Pattern**                                      |
|------------------------|---------------------------------------------------------|----------------------------------------------------------|
| Objetivo               | Criar objetos com base em parâmetros simples            | Construir objetos complexos com muitos atributos         |
| Forma de criação       | Objeto é entregue pronto                                | Objeto é montado passo a passo                           |
| Controle do cliente    | Baixo controle: recebe objeto finalizado                | Alto controle: personaliza antes de criar                |
| Complexidade de uso    | Baixa a média                                           | Média a alta                                              |
| Quando usar            | Tipos variados de objetos                               | Objetos com muitas etapas/configurações                  |

---

## ▶️ Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/factory-pattern-example.git
   ```

2. Acesse a pasta do projeto:
   ```bash
   cd factory-pattern-example
   ```

3. Execute o projeto:
   ```bash
   node src/app.js
   ```

---
# Curiosidade:
Factory Pattern se assemelha mais ao Builder Pattern, pois ambos são voltados à criação de objetos e ajudam a desacoplar a construção do uso final deles.
O Factory Pattern cria objetos prontos com base em parâmetros, enquanto o Builder Pattern permite montar objetos complexos passo a passo de forma personalizada.


## Autores

- **Gabriel Araújo**  
- **Gabriel B. Zanon**  
- **Kauê H. C. Fidelis**  
- **Lucas G. Giachetto**  
- **Marcos V. Oliveira**

📍 *Amparo – SP*  
💼 *Estudantes de Análise e Desenvolvimento de Sistemas - SENAI*


---

## Licença

Este projeto está licenciado sob a **MIT License**.  
Sinta-se livre para usar, estudar e adaptar!

