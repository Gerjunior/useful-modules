### [](https://github.com/Gerjunior/useful-modules#nest-js)Nest Js

NestJs is a progressive Node.js framework for building efficient and scalable server-side applications.

**Instalation *_(global)_*** 
 `npm i -g @nestjs/cli` 
 **or**
  `yarn add global @nestjs/cli`

**Usage**  create the project

``nest new FreshStart cd FreshStart && npm run start``

Main.ts

```
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();

```

For more details, visit the official  [NestJs documentation](https://docs.nestjs.com/first-steps).