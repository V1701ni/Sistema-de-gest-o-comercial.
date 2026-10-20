<div align="center">

# 🏢 Sistema de Gestão Comercial

**Sistema em console, feito em Java com orientação a objetos, para administrar clientes, fornecedores, produtos e pedidos de venda**

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![POO](https://img.shields.io/badge/Orienta%C3%A7%C3%A3o%20a%20Objetos-4A5C58?style=for-the-badge)
![Console](https://img.shields.io/badge/Aplica%C3%A7%C3%A3o-Console-181717?style=for-the-badge)

</div>

---

## Sobre o projeto

Projeto acadêmico, desenvolvido em grupo, que cobre o ciclo completo de uma operação comercial: do cadastro de clientes e fornecedores até a emissão de pedidos de venda. Toda a interação acontece pelo terminal, por meio de um menu numerado, e os dados ficam salvos em arquivos de texto, sem necessidade de banco de dados.

O foco do trabalho foi aplicar os conceitos de **Programação Orientada a Objetos** em um sistema com regras de negócio reais.

## Funcionalidades

- **Pessoas:** cadastro, listagem, alteração e exclusão de clientes, fornecedores ou ambos
- **Endereços:** vários endereços por pessoa, classificados como comercial, residencial, entrega ou correspondência
- **Produtos:** controle de descrição, custo, preço de venda e fornecedor
- **Pedidos:** cliente, endereço de entrega e itens, com cálculo automático do subtotal e do total
- **Validações:** as regras de cada cadastro são conferidas antes de salvar, com mensagens de erro claras
- **Registro de operações:** as ações realizadas são gravadas em um arquivo de log
- **Interface no terminal:** menu organizado em blocos, com cores e cabeçalho

## Menu do sistema

| Bloco | Opções |
| --- | --- |
| Pessoas | 1 Cadastrar · 2 Listar · 3 Alterar · 4 Excluir |
| Produtos | 5 Cadastrar · 6 Listar · 7 Alterar · 8 Excluir |
| Pedidos | 9 Cadastrar · 10 Listar · 11 Alterar · 12 Excluir |
| Endereços | 13 Listar · 14 Cadastrar · 15 Alterar · 16 Excluir |
| Sair | 0 |

## Conceitos de POO aplicados

- **Classe abstrata:** `Entidade` define a base (código e resumo) das classes persistentes
- **Herança:** `Pessoa` e `Produto` estendem `Entidade`
- **Interfaces:** `Validavel`, `Buscavel`, `Resumivel` e `Repositorio<T>`
- **Polimorfismo:** cada entidade implementa o próprio `resumo()`
- **Enums:** `TipoPessoa` e `TipoEndereco`
- **Singleton:** os repositórios são acessados por `getInstancia()`
- **Encapsulamento:** atributos privados com getters e setters
- **Organização em camadas:** aplicação, modelo, repositório e utilitários separados

## Estrutura do projeto

```text
.
├── src/
│   ├── Aplicacao/     # Main e controladores (Pessoa, Produto, Pedido)
│   ├── Modelo/        # Entidades e enums (Pessoa, Endereco, Produto, Pedido, ItemPedido...)
│   ├── repository/    # Repositórios e interfaces (persistência em arquivos de texto)
│   └── Utilitario/    # Teclado, DesignUI, GerenciadorMenu e GerenciadorLog
└── data/              # Arquivos de dados: pessoas, enderecos, produtos, pedidos, menus e log
```

## Como executar

### Pré-requisitos

- [JDK 17](https://adoptium.net/) ou superior

### Pelo IntelliJ IDEA

1. Abra a pasta do projeto no IntelliJ.
2. Abra o arquivo `src/Aplicacao/Main.java` e execute o método `main`.

> Execute sempre a partir da **pasta raiz** do projeto, porque o sistema lê os arquivos em `./data`.

### Pelo terminal

Clone o repositório e entre na pasta:

```bash
git clone https://github.com/V1701ni/Sistema-de-gest-o-comercial..git
cd Sistema-de-gest-o-comercial.
```

Compile (Linux e macOS):

```bash
javac -d out -encoding UTF-8 $(find src -name "*.java")
```

Compile (Windows, PowerShell):

```powershell
javac -d out -encoding UTF-8 (Get-ChildItem -Recurse src -Filter *.java).FullName
```

Execute:

```bash
java -Dfile.encoding=UTF-8 -cp out Aplicacao.Main
```

> No Windows, se os acentos e as molduras do menu aparecerem quebrados, rode `chcp 65001` no terminal antes de executar.

## Dados de exemplo

A pasta `data/` já vem com pessoas, endereços, produtos e pedidos de exemplo, para o sistema ser testado logo na primeira execução.

## Contexto acadêmico

Trabalho desenvolvido na disciplina de Desenvolvimento de Software, do curso de Sistemas de Informação da Universidade Positivo. Este repositório é um fork do projeto original do grupo: [Trabalho-Desenvolvimento-de-Software](https://github.com/Sid12Zzz/Trabalho-Desenvolvimento-de-Software).
