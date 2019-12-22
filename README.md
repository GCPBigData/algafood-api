
# AlgaFood API - Projeto REST/API - Utilizando Spring Boot

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://">
  </a>
  <h3 align="center">AlgaFood API (REST)</h3>
</p>



<!-- TABLE OF CONTENTS -->

## Tabela de Conteúdo

- [Tabela de Conteúdo](#tabela-de-conte%C3%BAdo)
- [Sobre o Projeto](#sobre-o-projeto)
  - [Feito Com](#feito-com)
- [Começando](#come%C3%A7ando)
  - [Pré-requisitos](#pr%C3%A9-requisitos)
  - [Estrutura de Arquivos](#estrutura-de-arquivos)
  - [Instalação](#instala%C3%A7%C3%A3o)
  - [Edição](#edi%C3%A7%C3%A3o)
  - [Publicação](#publica%C3%A7%C3%A3o)
- [Contribuição](#contribui%C3%A7%C3%A3o)
- [Licença](#licen%C3%A7a)
- [Contato](#contato)

<!-- ABOUT THE PROJECT -->

## Sobre o Projeto

Projeto AlgaFood API - uma API (REST) para delivery de comida.
Curso: AlgaWorks - Especialista em Spring REST - https://cafe.algaworks.com/lista-espera-spring-rest/

### Feito Com

Tecnologias utilizadas no projeto

- [JAVA](https://www.java.com/pt_BR/download/) - Java é uma linguagem de programação e plataforma computacional lançada pela primeira vez pela Sun Microsystems em 1995. Existem muitas aplicações e sites que não funcionarão, a menos que você tenha o Java instalado, e mais desses são criados todos os dias;
- [Spring Boot](https://spring.io/projects/spring-boot) - O Spring Boot é um projeto da Spring que veio para facilitar o processo de configuração e publicação de nossas aplicações. A intenção é ter o seu projeto rodando o mais rápido possível e sem complicação;
- [Flyway DB](https://flywaydb.org/getstarted/) - Flyway é uma dentre as várias ferramentas que se propõem a trazer ordem e organização para os scripts SQL que são executados no banco de dados, funcionando como um controle de versão do mesmo;


<!-- GETTING STARTED -->

## Começando

Para reproduzir o exemplo, é necessário seguir os requisitos mínimos.

### Pré-requisitos

 - Você vai precisar de uma IDE como por exemplo: IntelliJ IDEA, Eclipse, VSCode.
 - Instale a JDK 11+
 - Instale o Apache Maven 3.5.3+ ou o Gradle

 #### Docker
 - Escolha um cliente para conectar com o Banco de dados, exemplo: DBeaver
 - Cliente para realizar requisições REST: Postman ou o Insomnia.
 - Instruções Adicionais:
 - Instalação do Docker (Documentação oficial)
 - Instalando Docker no windows: (Youtube, ESR)
 - Instalando o Docker no Linux: (Youtube: LinuxTips)
 - Instalando o Docker no Mac: (Youtube: Wellington Rogati)

### Estrutura de Arquivos

A estrutura de arquivos está da seguinte maneira:

```bash
├── README.md
├── mvnw
├── mvnw.cmd
├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── algaworks
│   │   │           └── algafood
│   │   │               ├── AlgafoodApiApplication.java
│   │   │               ├── api
│   │   │               │   └── controller
│   │   │               │       ├── CidadeController.java
│   │   │               │       ├── CozinhaController.java
│   │   │               │       ├── EstadoController.java
│   │   │               │       ├── RestauranteController.java
│   │   │               │       └── TesteController.java
│   │   │               ├── domain
│   │   │               │   ├── exception
│   │   │               │   │   ├── EntidadeEmUsoException.java
│   │   │               │   │   └── EntidadeNaoEncontradaException.java
│   │   │               │   ├── model
│   │   │               │   │   ├── Cidade.java
│   │   │               │   │   ├── Cozinha.java
│   │   │               │   │   ├── Endereco.java
│   │   │               │   │   ├── Estado.java
│   │   │               │   │   ├── FormaPagamento.java
│   │   │               │   │   ├── Grupo.java
│   │   │               │   │   ├── ItemPedido.java
│   │   │               │   │   ├── Pedido.java
│   │   │               │   │   ├── Permissao.java
│   │   │               │   │   ├── Produto.java
│   │   │               │   │   ├── Restaurante.java
│   │   │               │   │   ├── StatusPedido.java
│   │   │               │   │   └── Usuario.java
│   │   │               │   ├── repository
│   │   │               │   │   ├── CidadeRepository.java
│   │   │               │   │   ├── CozinhaRepository.java
│   │   │               │   │   ├── CustomJpaRepository.java
│   │   │               │   │   ├── EstadoRepository.java
│   │   │               │   │   ├── FormaPagamentoRepository.java
│   │   │               │   │   ├── PermissaoRepository.java
│   │   │               │   │   ├── RestauranteRepository.java
│   │   │               │   │   └── RestauranteRepositoryQueries.java
│   │   │               │   └── service
│   │   │               │       ├── CadastroCidadeService.java
│   │   │               │       ├── CadastroCozinhaService.java
│   │   │               │       ├── CadastroEstadoService.java
│   │   │               │       └── CadastroRestauranteService.java
│   │   │               └── infrastructure
│   │   │                   └── repository
│   │   │                       ├── CustomJpaRepositoryImpl.java
│   │   │                       ├── RestauranteRepositoryImpl.java
│   │   │                       └── spec
│   │   │                           └── RestauranteSpecs.java
│   │   └── resources
│   │       ├── META-INF
│   │       │   └── orm.xml
│   │       ├── application.properties
│   │       ├── db
│   │       │   ├── migration
│   │       │   │   ├── V001__criacao-inicial.sql
│   │       │   │   ├── V002__cria-tabela-cidade.sql
│   │       │   │   ├── V003__cria-tabela-estado.sql
│   │       │   │   ├── V004__cria-varias-tabelas.sql
│   │       │   │   ├── V005__cria-tabela-teste.sql
│   │       │   │   ├── V006__remove-tabela-teste.sql
│   │       │   │   └── V007__cria-tabelas-pedido-item-pedido.sql
│   │       │   └── testdata
│   │       │       └── afterMigrate.sql
│   │       └── flyway.properties
│   └── test
│       └── java
│           └── com
│               └── algaworks
│                   └── algafood
│                       └── AlgafoodApiApplicationTests.java
└── target
    ├── classes
    │   ├── META-INF
    │   │   ├── MANIFEST.MF
    │   │   ├── maven
    │   │   │   └── com.algaworks
    │   │   │       └── algafood-api
    │   │   │           ├── pom.properties
    │   │   │           └── pom.xml
    │   │   └── orm.xml
    │   ├── application.properties
    │   ├── com
    │   │   └── algaworks
    │   │       └── algafood
    │   │           ├── AlgafoodApiApplication.class
    │   │           ├── api
    │   │           │   └── controller
    │   │           │       ├── CidadeController.class
    │   │           │       ├── CozinhaController.class
    │   │           │       ├── EstadoController.class
    │   │           │       ├── RestauranteController.class
    │   │           │       └── TesteController.class
    │   │           ├── domain
    │   │           │   ├── exception
    │   │           │   │   ├── EntidadeEmUsoException.class
    │   │           │   │   └── EntidadeNaoEncontradaException.class
    │   │           │   ├── model
    │   │           │   │   ├── Cidade.class
    │   │           │   │   ├── Cozinha.class
    │   │           │   │   ├── Endereco.class
    │   │           │   │   ├── Estado.class
    │   │           │   │   ├── FormaPagamento.class
    │   │           │   │   ├── Grupo.class
    │   │           │   │   ├── ItemPedido.class
    │   │           │   │   ├── Pedido.class
    │   │           │   │   ├── Permissao.class
    │   │           │   │   ├── Produto.class
    │   │           │   │   ├── Restaurante.class
    │   │           │   │   ├── StatusPedido.class
    │   │           │   │   └── Usuario.class
    │   │           │   ├── repository
    │   │           │   │   ├── CidadeRepository.class
    │   │           │   │   ├── CozinhaRepository.class
    │   │           │   │   ├── CustomJpaRepository.class
    │   │           │   │   ├── EstadoRepository.class
    │   │           │   │   ├── FormaPagamentoRepository.class
    │   │           │   │   ├── PermissaoRepository.class
    │   │           │   │   ├── RestauranteRepository.class
    │   │           │   │   └── RestauranteRepositoryQueries.class
    │   │           │   └── service
    │   │           │       ├── CadastroCidadeService.class
    │   │           │       ├── CadastroCozinhaService.class
    │   │           │       ├── CadastroEstadoService.class
    │   │           │       └── CadastroRestauranteService.class
    │   │           └── infrastructure
    │   │               └── repository
    │   │                   ├── CustomJpaRepositoryImpl.class
    │   │                   ├── RestauranteRepositoryImpl.class
    │   │                   └── spec
    │   │                       └── RestauranteSpecs.class
    │   ├── db
    │   │   ├── migration
    │   │   │   ├── V001__criacao-inicial.sql
    │   │   │   ├── V002__cria-tabela-cidade.sql
    │   │   │   ├── V003__cria-tabela-estado.sql
    │   │   │   ├── V004__cria-varias-tabelas.sql
    │   │   │   ├── V005__cria-tabela-teste.sql
    │   │   │   ├── V006__remove-tabela-teste.sql
    │   │   │   └── V007__cria-tabelas-pedido-item-pedido.sql
    │   │   └── testdata
    │   │       └── afterMigrate.sql
    │   └── flyway.properties
    ├── generated-sources
    │   └── annotations
    ├── generated-test-sources
    │   └── test-annotations
    └── test-classes
        └── com
            └── algaworks
                └── algafood
                    └── AlgafoodApiApplicationTests.class

56 directories, 103 files
```

#### Executando a Instância do MySql no Docker 

Para iniciar o MySql, basta rodar o comando abaixo (O Docker precisa estar instalado): 

```sh
docker run --name algafood-mysql -v /Users/marcus/Developer/Database_Docker/MySQL:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql
```

<!-- CONTRIBUTING -->

## Contribuição

Fique a vontade para contribuir com o projeto.

1. Faça um Fork do projeto
2. Crie uma Branch para sua Feature (`git checkout -b feature/newFeature`)
3. Adicione suas mudanças (`git add .`)
4. Comite suas mudanças (`git commit -m 'Nova funcionalidade para facilitar ...`)
5. Faça o Push da Branch (`git push origin feature/newFeature`)
6. Abra um Pull Request

<!-- LICENSE -->

## Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

<!-- CONTACT -->

## Contato

Marcus Paulo - [Github](https://github.com/marcuspaulo)