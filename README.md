# MathExp - Interpretador de Expressões Matemáticas

Um interpretador de expressões matemáticas simples implementado em Python. Este projeto demonstra conceitos fundamentais de compiladores e interpretadores, focando na análise léxica e sintática de expressões matemáticas.

## Funcionalidades

- Análise léxica (tokenização) de expressões matemáticas
- Análise sintática com construção de árvore sintática abstrata (AST)
- Suporte para operações aritméticas básicas (+, -, *, /)
- Suporte para potenciação (^) com associatividade à direita
- Respeito à precedência de operadores
- Suporte para parênteses para agrupar expressões
- Interface de linha de comando interativa (REPL)

## Gramática Suportada

```
<Exp> ::= <Term> ((MINUS | PLUS) <Term>)*
<Term> ::= <Factor> ((MUL | DIV) <Factor>)*
<Factor> ::= (PLUS | MINUS)* <Factor> | <Pow>
<Pow> ::= <Atom> (POW <Pow>)*
<Atom> ::= INT | FLOAT | LPAR <Exp> RPAR
```

## Requisitos

- Python 3.x

## Instalação

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/mathexpr.git
cd mathexpr
```

## Uso

Execute o programa principal:

```bash
python main.py
```

### Comandos do REPL

- Digite expressões matemáticas para avaliação
- `:h` - Exibe ajuda
- `:s` - Mostra exemplos de expressões
- `:q` - Sai do programa

### Exemplos

```
UFC> 1+3*8*(1+2)
UFC> 2^3^2
```

## Estrutura do Projeto

- `main.py` - Ponto de entrada do programa
- `Repl.py` - Interface de linha de comando interativa
- `Lexer.py` - Analisador léxico que converte texto em tokens
- `Parser.py` - Analisador sintático que constrói a AST
- `Grammar.py` - Define as regras gramaticais da linguagem
- `Consts.py` - Define constantes e tokens
- `SemanticVisitor.py` - Implementa o padrão visitor para a AST
- `Token.py` - Define a classe Token
- `Error.py` - Tratamento de erros
- `TValue.py` - Representa valores tipados
- `Util.py` - Funções utilitárias

## Como Funciona

1. O usuário insere uma expressão matemática
2. O Lexer divide a expressão em tokens
3. O Parser organiza os tokens em uma árvore sintática seguindo as regras gramaticais
4. A estrutura da expressão é exibida para o usuário

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## Licença

[MIT](LICENSE)
