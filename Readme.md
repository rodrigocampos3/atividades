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
    - Cole o codigo abaixo:
    -
   ```python
    import json

    def lambda_handler(event, context):
        headers = event.get('headers', {})
        codigo_autenticacao_esperado = "userAutenticado"
        if 'Codigo-Autenticacao' in headers and headers['Codigo-Autenticacao'] == codigo_autenticacao_esperado:
            return {
                'statusCode': 200,
                'body': event["body"]
            }
        else:
            return {
                'statusCode': 401,
                'body': json.dumps({'message': 'Acesso não autorizado'})
            }
    ```
O código acima trata-se de uma requisição POST que recebe um JSON e, em seguida, retorna o mesmo JSON. Para acessar a rota, é necessário que o cabeçalho contenha a chave "Codigo-Autenticacao" com o valor correto, que seria "userAutenticado".
  - Clique em "Criar função" para criar a função Lambda.

3. **Criação do API Gateway:**

    - Acesse o Console da AWS.
    - Navegue até o serviço Amazon API Gateway.
    - Clique em "Criar API".
    - Escolha o tipo de REST API
    - Configure as opções da API, como nome e descrição.
    - Crie um recurso e um método para a API.
    - Associe o método à função Lambda criada anteriormente.
    - Clique em "Implantar a API" para criar um estágio de implantação.

4. **Teste da API:**

     ```bash
        curl -X POST -H "Content-Type: application/json" -H "Codigo-Autenticacao: userAutenticado" -d '{"chave1": "valor1", "chave2": "valor2"}' https://sua-url-da-api-gateway.execute-api.sua-regiao.amazonaws.com/seu-recurso
é esperado que receba o json com os valor da chave1 e chave2 como resposta, caso isso ocorra está tudo certo com sua função


5. **Teste da minha lambda function**

    ```bash
       curl -X POST -H "Content-Type: application/json" -H "Codigo-Autenticacao: userAutenticado" -d '{"chave1": "valor1", "chave2": "valor2"}' https://puija78sw4.execute-api.us-east-1.amazonaws.com/default/MansurPost

Copie e cole este CURL no postman para testar minha função, caso os valores de chave1 e chave2 sejam retornados deu tudo certo, tente alterar o codigo de autencicação e verá que a requisição será bloqueada
## Recursos Adicionais

- [Documentação oficial da AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Documentação oficial do Amazon API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)

## Autores

- Rodrigo Campos Rodrigues

