# Visão Geral da Arquitetura

## Introdução

Este documento descreve a arquitetura do sistema de software Metakyasshu. O sistema é composto por um conjunto de
módulos responsáveis por diferentes funcionalidades. A arquitetura é composta por três camadas: a camada de
apresentação, a camada de negócio e a camada de dados. A camada de apresentação é responsável por apresentar as
informações ao usuário, a camada de negócio é responsável por implementar as regras de negócio e a camada de dados é
responsável por armazenar os dados do sistema.

**- Camada de Apresentação:** Responsável pela interface do usuário e pela interação com o usuário.
**- Camada de Negócio:** Encapsula as regras de negócio e lógica da aplicação.
**- Camada de Dados:** Acessa e gerência os dados persistentes do sistema.

## Camada de Apresentação

A camada de apresentação é implementada usando o framework Angular. Ela é responsável por:

- Exibir interfaces de usuário: Criar telas dinâmicas e interativas para os usuários interagirem com o sistema.
- Gerenciar o estado da aplicação: Manter o estado da aplicação e atualizar a interface do usuário conforme as ações do
  usuário.
- Comunicar com a camada de negócio: Fazer requisições à camada de negócio para obter e atualizar dados.

A camada de apresentação se comunica com a camada de negócio por uma API RESTful. A API define os endpoints e formatos
de dados para a comunicação entre as camadas.

## Camada de Negócio

A camada de negócio é implementada usando o framework Spring. Ela é responsável por:

- Implementar as regras de negócio: Aplicar as regras de negócio da aplicação para processar dados e tomar decisões.
- Gerenciar a lógica da aplicação: Executar a lógica da aplicação para realizar as tarefas do sistema.
- Comunicar com a camada de dados: Acessar e atualizar os dados persistentes do sistema.

A camada de negócio se comunica com a camada de dados através do Data Access Object (DAO) padrão do Spring. O DAO
fornece métodos para acessar e manipular dados no banco de dados MySQL.

## Camada de Dados

A camada de dados é implementada usando o banco de dados relacional MySQL. Ela é responsável por:

- Armazenar dados persistentes: Armazenar os dados da aplicação de forma segura e confiável.
- Gerenciar dados: Fornecer mecanismos para acessar, inserir, atualizar e excluir dados.
- Garantir a integridade dos dados: Garantir a consistência e integridade dos dados armazenados.

A camada de dados é acessada pela camada de negócio através do DAO do Spring. O DAO encapsula as interações com o banco
de dados e fornece uma abstração para a camada de negócio.

## Implementação Tecnológica

- Linguagem de programação: Java
- Framework de apresentação: Angular
- Framework de negócio: Spring
- Banco de dados: MySQL
- Servidor de aplicação: Apache Tomcat