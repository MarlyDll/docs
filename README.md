# Inmemori Http REST API  

### Server

| Env        | Url                              |
|------------|----------------------------------|
| production | `https://api.inmemori.com`       |
| dev        | `https://api.inmemori-dev.com`   |

### Authentification

Ajoutez votre `apikey` dans le `body` ou la `query` à chaque requêtes. 

exemple: `/endpoint?token={yourapikey}`
  
  
<br/>

## Créer une page  

### `POST /users description`

| Fields          | Type           | Info                | ex:                            |
|-----------------|----------------|---------------------|--------------------------------|
| firstname       | `string`       | required            |                                |
| lastname        | `string`       | required            |                                |
| email           | `string`       |                     |                                |
| gender          | `string`       | `m` or `f`          |                                |
| dob             | `isodate`      | date of birth       | 1986-12-19T00:00:00.000Z       |
| dod             | `isodate`      | date of death       | 2018-12-19T00:00:00.000Z       |
| places          | `array`        | if places info exist|                                |

### `POST /places description - array 1`

| Fields          | Type           | Info                | ex:                            |
|-----------------|----------------|---------------------|--------------------------------|
| name            | `string`       |                     |                                |
| date            | `isodate`      | date of event 1     | 2018-12-19T10:45:00.000Z       |
| address         | `string`       |                     |                                |
| type            | `string`       | `ceremony` or `contemplation` or `interment` or `cremation`|                                |


### `POST /places description - array 2`

| Fields          | Type           | Info                | ex:                            |
|-----------------|----------------|---------------------|--------------------------------|
| name            | `string`       |                     |                                |
| date            | `isodate`      | date of event 2     | 2018-12-19T11:45:00.000Z       |
| address         | `string`       |                     |                                |
| type            | `string`       | `ceremony` or `contemplation` or `interment` or `cremation`|                                |


### Exemple

  ```curl
    curl -X POST 'https://api.inmemori-dev.com/users' \
      -H 'content-type: application/json' \
      -d '{ "firstname": "paul", "lastname": "cezane" }'
  ```
