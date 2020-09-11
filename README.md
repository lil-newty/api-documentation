# Cria Admin de Principal

É uma request que só precisa ser feita em caso em que o banco de dados está vazio ou em que o main_adm foi apagado.

**URL** : `/admin/cadastro/debug/`

**Method** : `POST`

**Auth required** : NO

**Permissions required** : None

**Data constraints** : `{}`

## Success Responses

**Condition** : Não existe main_adm no banco de dados

**Code** : `201 OK`

**Content** : 

```json
{
  "id": 12,
  "nome": "main_adm",
  "email": "igor.holanda.main@gmail.com"
}
```
