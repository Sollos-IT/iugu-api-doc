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
    "x-access-token": "seu_token_de_acesso"
  }
}
```

## Rota de gerar assinatura

Esta rota permite que o usuário gere uma assinatura RSA.

### Requisição

Envie um JSON com seu body a ser assinado. Segue um exemplo:

```json
{
  "amount": 23,
  "pixKey": 77991922123,
  "pixKeyType": "TEL"
}
```

### Resposta

Uma resposta bem-sucedida retornará sua assinatura e mais alguns dados. Exemplo de resposta:

```json
{
  "message": "Assinatura digital gerada com sucesso",
  "assinatura": "LDITD5WsfasfRHxuraozI+a686iWv6QJxRuAmMmZhnl1swAS/yIzwuqr3LnS0+fY1HaledokUmwCe+hI2PlR9fE6gLaeCbg2Rfkur/jLGG+RoOJ0vQiaM+5NRlCQHIHXTjVFD7J3me6IjK3Y5gcxt6mL22b6DJ9ZXPM8C7yyNk4TUwEgtF3UJivGCdugtsWyGVdMSN1pEUXMlSxSY2EEi09yvWedcsds0tcRyRcT5Jm7zpFPUj95lD1VhWtdeiJRB4f4blMXaMF/ZkeZ9bUzySulMpaikjtYIayKTMfWchC5aasdaw1tAZNZaSKFpCnaX9Jy0EHWLEUFvEmcdUSQ==",
  "request_time": "2025-04-08T12:53:30-03:00",
  "body": {
    "amount": 23,
    "pixKey": 77991922123,
    "pixKeyType": "TEL"
  }
}
```
