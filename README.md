![logo jodita](https://github.com/SoraBeat/JoditaDB/blob/dev/logojoditabackground.png?raw=true)

# API Jodita

Welcome to the Jodita API, in this section we will talk about its operation, characteristics and others. Below everything you will find links so that you can contact you in case you have any questions or recommendations. All messages are welcome!. To take into account: for public requests it is necessary to register and log in since a valid token is needed. This API is still under development.

## Visual

You can see the layout of the project in our figma:
[Click here](https://www.figma.com/file/8FpoEIvou24AzP69NVKBYx/Jodita?node-id=0%3A1&t=v4ODLD8I5gEQdtAV-1)

![example visual](https://github.com/SoraBeat/JoditaDB/blob/dev/visualexample.png?raw=true)

## DEMO

This api is already running online! Try it if you want!
[Click here](https://joditadb.vercel.app/)

## API References

## Auth

```http
  POST /api/public/login
```

| Parameter  | Type     | Description   |
| :--------- | :------- | :------------ |
| `email`    | `string` | **Required**. |
| `password` | `string` | **Required**  |

```http
  POST /api/public/register
```

| Parameter  | Type     | Description   |
| :--------- | :------- | :------------ |
| `email`    | `string` | **Required**. |
| `password` | `string` | **Required**  |
| `userName` | `string` | **Required**  |
| `image`    | `base64` | **Optional**  |

```http
  POST /api/public/logout
```

With this command you close session

## Users ADMIN

**These requests requires ADMIN permissions**

```http
  GET /api/private/users
```

| Parameter | Type      | Description   |
| :-------- | :-------- | :------------ |
| `search`  | `string`  | **Optional**. |
| `isAdmin` | `boolean` | **Optional**  |
| `skip`    | `number`  | **Optional**. |
| `limit`   | `number`  | **Optional**  |

```http
  GET /api/private/user/:userId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

```http
  POST /api/private/user
```

| Parameter   | Type      | Description   |
| :---------- | :-------- | :------------ |
| `email`     | `string`  | **Required**. |
| `password`  | `string`  | **Required**  |
| `userName`  | `string`  | **Required**  |
| `isAdmin`   | `boolean` | **Required**  |
| `isPremium` | `boolean` | **Required**  |
| `wasBanned` | `boolean` | **Required**  |
| `image`     | `base64`  | **Optional**  |

```http
  PUT /api/private/user/:userId
```

| Parameter   | Type       | Description   |
| :---------- | :--------- | :------------ |
| `userId`    | `ObjectID` | **Required**. |
| `email`     | `string`   | **Required**. |
| `password`  | `string`   | **Required**  |
| `userName`  | `string`   | **Required**  |
| `isAdmin`   | `boolean`  | **Required**  |
| `isPremium` | `boolean`  | **Required**  |
| `wasBanned` | `boolean`  | **Required**  |
| `image`     | `base64`   | **Optional**  |

```http
  DELETE /api/private/user/:userId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

## Users

```http
  GET /api/public/users
```

| Parameter | Type     | Description   |
| :-------- | :------- | :------------ |
| `search`  | `string` | **Optional**. |
| `skip`    | `number` | **Optional**. |
| `limit`   | `number` | **Optional**  |

```http
  GET /api/public/user/:userId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

## Follow

```http
  PUT /api/public/follow
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

```http
  PUT /api/public/unfollow
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

## Premium ADMIN

**These requests requires ADMIN permissions**

```http
  PUT /api/private/addPremium
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

```http
  PUT /api/private/removePremium
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

## Report ADMIN

**These requests requires ADMIN permissions**

```http
  GET /api/private/reportPerson
```

```http
  GET /api/private/reportProblem
```

## Report

```http
  POST /api/public/reportPerson
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `userId`  | `ObjectID` | **Required**. |

```http
  POST /api/private/reportProblem
```

| Parameter     | Type     | Description   |
| :------------ | :------- | :------------ |
| `problemType` | `string` | **Required**. |
| `description` | `string` | **Optional**. |

## Events ADMIN

**These requests requires ADMIN permissions**

```http
  GET /api/private/events
```

| Parameter   | Type      | Description   |
| :---------- | :-------- | :------------ |
| `search`    | `string`  | **Optional**. |
| `isPremium` | `boolean` | **Optional**  |
| `skip`      | `number`  | **Optional**. |
| `limit`     | `number`  | **Optional**  |

```http
  GET /api/private/user/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

```http
  POST /api/private/event
```

| Parameter     | Type       | Description   |
| :------------ | :--------- | :------------ |
| `userId`      | `ObjectID` | **Required**. |
| `title`       | `string`   | **Required**  |
| `description` | `string`   | **Required**  |
| `place`       | `string`   | **Required**  |
| `eventType`   | `string`   | **Required**  |
| `capacity`    | `number`   | **Required**  |
| `tags`        | `array`    | **Required**  |
| `datetime`    | `date`     | **Required**  |
| `price`       | `number`   | **Required**  |
| `isPremium`   | `boolean`  | **Required**  |
| `image`       | `base64`   | **Optional**  |

```http
  PUT /api/private/event/:eventId
```

| Parameter     | Type       | Description   |
| :------------ | :--------- | :------------ |
| `eventId`     | `ObjectID` | **Required**. |
| `userId`      | `ObjectID` | **Required**. |
| `title`       | `string`   | **Required**  |
| `description` | `string`   | **Required**  |
| `place`       | `string`   | **Required**  |
| `eventType`   | `string`   | **Required**  |
| `capacity`    | `number`   | **Required**  |
| `tags`        | `array`    | **Required**  |
| `datetime`    | `date`     | **Required**  |
| `price`       | `number`   | **Required**  |
| `isPremium`   | `boolean`  | **Required**  |
| `image`       | `base64`   | **Optional**  |

```http
  DELETE /api/private/event/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

## Events

```http
  GET /api/public/events
```

| Parameter       | Type       | Description   |
| :-------------- | :--------- | :------------ |
| `search`        | `string`   | **Optional**. |
| `isPremium`     | `boolean`  | **Optional**  |
| `orderByHearts` | `boolean`  | **Optional**  |
| `eventType`     | `string`   | **Optional**  |
| `onlyFree`      | `boolean`  | **Optional**  |
| `tag`           | `string`   | **Optional**  |
| `lastCreated`   | `boolean`  | **Optional**  |
| `skip`          | `number`   | **Optional**. |
| `limit`         | `number`   | **Optional**  |
| `userId`        | `ObjectID` | **Optional**  |

```http
  GET /api/public/event/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

```http
  POST /api/public/event
```

| Parameter     | Type     | Description  |
| :------------ | :------- | :----------- |
| `title`       | `string` | **Required** |
| `description` | `string` | **Required** |
| `place`       | `string` | **Required** |
| `eventType`   | `string` | **Required** |
| `capacity`    | `number` | **Required** |
| `tags`        | `array`  | **Required** |
| `datetime`    | `date`   | **Required** |
| `price`       | `number` | **Required** |
| `image`       | `base64` | **Optional** |

```http
  PUT /api/public/event/:eventId
```

| Parameter     | Type       | Description   |
| :------------ | :--------- | :------------ |
| `eventId`     | `ObjectID` | **Required**. |
| `title`       | `string`   | **Required**  |
| `description` | `string`   | **Required**  |
| `place`       | `string`   | **Required**  |
| `eventType`   | `string`   | **Required**  |
| `capacity`    | `number`   | **Required**  |
| `tags`        | `array`    | **Required**  |
| `datetime`    | `date`     | **Required**  |
| `price`       | `number`   | **Required**  |
| `image`       | `base64`   | **Optional**  |

```http
  DELETE /api/public/event/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

```http
  GET /api/public/myEvents
```

```http
  GET /api/public/myFavorites
```

```http
  PUT /api/public/addFavorite/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

```http
  PUT /api/public/removeFavorite/:eventId
```

| Parameter | Type       | Description   |
| :-------- | :--------- | :------------ |
| `eventId` | `ObjectID` | **Required**. |

## ⚒️Developer

Esta API ha sido realizada por:

### Lautaro Elian Roa Mazzola

- Github: [https://github.com/SoraBeat]()
- Linkedin: [https://www.linkedin.com/in/lautaro-elian-roa-mazzola-b30247209/]()

## ⚒️Collaborators

### Matias Juarez

- Linkedin: [https://www.linkedin.com/in/matias2707/]()

### Gerardo Alegre

- Linkedin: [https://www.linkedin.com/in/gerardo-alegre-333182177/]()
