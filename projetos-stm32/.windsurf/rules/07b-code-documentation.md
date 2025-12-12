---
trigger: always_on
description: Deve ser observada para documentação de código
---

## Documentação de código

* **Documente sempre**: variáveis, parâmetros, constantes, funções e classes, no código.
* **Explique decisões**: registre a motivação de algoritmos, estruturas e blocos de código (trade-offs, complexidade, limites).
* **Tom didático**: escreva de forma clara e instrutiva, acessível a quem é leigo.
* **Idioma**: toda a documentação em **português brasileiro**.
* **Localização**: mantenha a documentação em `./docs/` na raiz do projeto.

### Boas práticas de anotação no código

* **JavaScript/TypeScript**: use **JSDoc**/**TypeDoc** em funções, classes e módulos.
* **C/C++ (firmware)**: use **Doxygen** nas APIs públicas e módulos críticos.
* **Estrutura mínima de docstring/JSDoc**: objetivo, parâmetros, retorno, erros, efeitos colaterais, complexidade (quando relevante) e links para specs internas.

## Didática (orientação editorial)

* Escreva para **leigos** conseguirem **reproduzir tarefas** sem suporte.
* Use **passos numerados**, **capturas de tela** quando necessário e **tabelas** para variáveis/URLs.
* Destaque **avisos importantes** (e.g., segurança, limites de API).
