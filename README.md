# Cria Primeiro Admin

É uma request que só precisa ser feita em caso em que o banco de dados está vazio ou em que o main_adm foi apagado.

**URL** : `/admin/cadastro/debug/`

**Method** : `POST`

**Auth required** : NO

**Permissions required** : None

## Success Responses

**Condition** : Não existe main_adm no banco de dados

**Code** : `201 OK`

**Response** : 

```json
{
  "id": 12,
  "nome": "main_adm",
  "email": "igor.holanda.main@gmail.com"
}
```
---
# Cria Novo Admin

Essa request envia um email para o novo admin e instancia ele no data base com o campo ativo = False e sem hash de senha.

**URL** : `/admin/cadastrar/{{ token }}/`

| Campo           | Tipo                                 |
| --------------- | ------------------------------------ |
| **nome**        | string(required)                     |
| **email**       | string(required)                     |
| **link**        | string(required)                     |

O link é referente a url base da págiana que o admin definirá sua senha e confirmará o seu cadastro.
No email ele receberá: 

**{{ link }}/{{ token }}/**

No exemplo abaixo receberá no email: ```https://www.google.com/{{ token }}```

**Method** : `POST`

**Auth required** : YES

**Fresh Token required** : YES

## Success Responses

**Condition** : Não existe main_adm no banco de dados

**Code** : `201 OK`

**Example Body**:

```json
{
	"nome":"Igor",
	"email":"igor.pereira@poli.ufrj.br",
	"link" : "https://www.google.com/"
}
```

**Response** : 

```json
{
  "id": 9,
  "nome": "Igor",
  "email": "igor.pereira@poli.ufrj.br"
}
```
