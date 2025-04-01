## Introdução
Este repositório contém a documentação da API, explicando como consumi-la e detalhando cada endpoint disponível, seus parâmetros e respostas esperadas.

## Rota de Login
Esta rota permite que o usuário realize o login no sistema. Para efetuá-lo, envie uma requisição utilizando o método `POST` para a rota `/login`.

### Requisição
Envie um JSON com os campos `username` e `password`. Segue um exemplo:

```json
{
    "username": "seu_usuario",
    "password": "sua_senha"
}
```

### Resposta
Uma resposta bem-sucedida retornará um token de acesso `x-access-token`, que deve ser utilizado no cabeçalho das próximas requisições. Exemplo de resposta:

```json
{
    "x-access-token": "seu_token_de_acesso"
}
```

### Exemplo de Header
Segue um exemplo de header utilizando o x-access-token, no formato JSON:

```json
{
    "headers": {
        "x-access-token": "seu_token_de_acesso",   
    }
}
```
