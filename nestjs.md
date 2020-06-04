# nest js

NestJs is a progressive Node.js framework for building efficient and scalable server-side applications.

## Installation
```npx -p @nestjs/cli nest new [project]```

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