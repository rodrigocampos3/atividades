# Guia para Criar uma Função Lambda e API Gateway

Este é um guia passo a passo para criar e implantar uma função Lambda e um API Gateway na AWS.

## Pré-requisitos

- Uma conta da AWS.
- AWS CLI instalada e configurada com credenciais apropriadas.
- Conhecimento de Python e AWS Lambda.

## Passos para Criação

Siga os passos abaixo para criar a função Lambda e o API Gateway:

1. **Criação da Função Lambda:**

    - Acesse o Console da AWS.
    - Navegue até o serviço AWS Lambda.
    - Clique em "Criar função" e selecione "Autor de Funções" adequado (por exemplo, "Author from scratch").
    - Configure as opções da função, como nome, runtime (Python, Node.js, etc.), e permissões.
    - Escreva ou faça upload do código da função.
    - Clique em "Criar função" para criar a função Lambda.

2. **Configuração de Variáveis de Ambiente (Opcional):**

    - Se a sua função depende de variáveis de ambiente, configure-as na guia "Variáveis de Ambiente" da função Lambda no Console da AWS.

3. **Criação do API Gateway:**

    - Acesse o Console da AWS.
    - Navegue até o serviço Amazon API Gateway.
    - Clique em "Criar API".
    - Escolha o tipo de API que você deseja criar (por exemplo, REST API).
    - Configure as opções da API, como nome e descrição.
    - Crie um recurso e um método para a API.
    - Associe o método à função Lambda criada anteriormente.
    - Clique em "Implantar a API" para criar um estágio de implantação.

4. **Teste da API:**

    - Teste a API usando o URL de invocação fornecido pelo API Gateway.

5. **Monitoramento e Logs:**

    - Configure o monitoramento e visualize os logs da função Lambda e do API Gateway no CloudWatch.

## Recursos Adicionais

- [Documentação oficial da AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Documentação oficial do Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)

## Autores

- Nome do autor

