## Introdução ao Drools

# 1. Visão Geral
Drools é uma solução de Sistema de Gerenciamento de Regras de Negócios (BRMS). Ele fornece um mecanismo de regras que processa fatos e produz saída como resultado de regras e processamento de fatos. A centralização da lógica de negócios torna possível introduzir mudanças de forma rápida e barata.

Ele também preenche a lacuna entre as equipes técnica e comercial, fornecendo uma facilidade para escrever as regras em um formato que seja fácil de entender.

# 2. Dependências Maven
Para começar com o Drools, precisamos primeiro adicionar algumas dependências em nosso pom.xml:

```
<dependency>
    <groupId>org.kie</groupId>
    <artifactId>kie-ci</artifactId>
    <version>7.1.0.Beta1</version>
</dependency>
<dependency>
    <groupId>org.drools</groupId>
    <artifactId>drools-decisiontables</artifactId>
    <version>7.1.0.Beta1</version>
</dependency>
```

A versão mais recente de ambas as dependências está disponível no Repositório Central Maven como kie-ci e drools-decisiontables.

3. Noções básicas do Drools
Veremos os conceitos básicos do Drools:

- Fatos - representa os dados que servem de entrada para as regras;
- Memória de Trabalho - um armazenamento com Fatos, onde são utilizados para o casamento de padrões e podem ser modificados, inseridos e removidos;
- Regra - representa uma única regra que associa fatos a ações correspondentes. Ele pode ser escrito em Drools Rule Language nos arquivos .drl ou como Decision Table em uma planilha do Excel;
- Sessão de Conhecimento - contém todos os recursos necessários para as regras de disparo; todos os fatos são inseridos na sessão e, em seguida, as regras correspondentes são disparadas;
- Base de Conhecimento - representa o conhecimento no ecossistema Drools, contém as informações sobre os recursos onde as Regras se encontram, e também cria a Sessão de Conhecimento;
- Módulo - Um módulo contém várias bases de conhecimento que podem conter diferentes sessões.

# 4. Configuração Java
Para disparar regras em um dado dado, precisamos instanciar as classes fornecidas pelo framework com informações sobre a localização dos arquivos de regras e os fatos:

### 4.1. KieFileSystem
Primeiro, precisamos definir o bean KieFileSystem; este é um sistema de arquivos na memória fornecido pela estrutura. O código a seguir fornece o contêiner para definir os recursos do Drools, como arquivos de regras, tabelas de decisão, programaticamente: