ORM : TypeORM 

ConfigModule: exposes ConfigService allows you to load the .env file. 
```bash
$ npm i --save @nestjs/config
```

> The `@nestjs/config` package internally uses [dotenv](https://github.com/motdotla/dotenv).

We then import that in the app.module.ts file

```js
import { Module } from '@nestjs/common';
import { ConfigModule } from '@nestjs/config';

@Module({
  imports: [ConfigModule.forRoot()],
})
export class AppModule {}


```
can use then process.env to not hard code the config

```typescript
  port: parseInt(process.env.PORT, 10) || 3000,
  database: {
    host: process.env.DATABASE_HOST,
    port: parseInt(process.env.DATABASE_PORT, 10) || 5432
  }
```


When building input validation types (also called DTOs), it's often useful to build **create** and **update** variations on the same type. For example, the **create** variant may require all fields, while the **update** variant may make all fields optional.

#### Implementing the "Sign in" endpoint

Our `AuthService` has the job of retrieving a user and verifying the password. We create a `signIn()` method for this purpose. In the code below, we use a convenient ES6 spread operator to strip the password property from the user object before returning it. This is a common practice when returning user objects, as you don't want to expose sensitive fields like passwords or other security keys.

## Pourquoi Argon2 > bcrypt ?

**Plus récent** : Gagnant du Password Hashing Competition 2015  
**Plus résistant** : Contre les attaques GPU et ASIC  
**Configurable** : Temps, mémoire, parallélisme  
**Recommandé** : Par l'OWASP pour les nouvelles applications

#### JWT token

We're ready to move on to the JWT portion of our auth system. Let's review and refine our requirements:

- Allow users to authenticate with username/password, returning a JWT for use in subsequent calls to protected API endpoints. We're well on our way to meeting this requirement. To complete it, we'll need to write the code that issues a JWT.
- Create API routes which are protected based on the presence of a valid JWT as a bearer token

We'll need to install one additional package to support our JWT requirements:

```bash

$ npm install --save @nestjs/jwt
```