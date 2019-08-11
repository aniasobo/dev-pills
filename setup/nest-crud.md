# Nest.js CRUD with Postgres and TypeORM

[Nest.js](https://nestjs.com/) - framework for writing Node/Express server-side backend; platform-agnostic, supports TypeScript  

[This tutorial](https://dev.to/rohanfaiyazkhan/nestjs-crud-with-postgres-cho)

### 1. Initial setup

```
$ npm i -g @nestjs/cli
$ nest new nest-app
```

### 2. Test run

```
$ cd nest-app
$ npm run start  // default port is 3000
```

### 3. Add your database to your `psql`

### 4. Connecting the app to the database  

```
npm add pg typeorm @nestjs/typeorm @nestjsx/crud
```

### 5. Create a config file in the root and call it `ormconfig.json`   

```
{
    "type": "postgres",
    "host": "localhost",
    "port": 5432,
    "username": "anna",
    "password": "password",
    "database": "anna",
    "entities": ["dist/**/*.entity.js"],
    "synchronize": true,
    "logging": true
}
```

### 6. Add this to `app.module.ts` file in `src`

```
import { Module } from '@nestjs/common'
import { AppController } from './app.controller'
import { AppService } from './app.service'
import { TypeOrmModule } from '@nestjs/typeorm'
import { EntityModule } from './entity/entity.module'

@Module({
    imports: [ TypeOrmModule.forRoot(), EntityModule],
    controllers: [ AppController ],
    providers: [ AppService ]
})
export class AppModule {}
```

### 7. Create your entity - create a directory `entityname` and in it, a file called `entityname.entity.ts`  

```
import { Entity, Column, PrimaryGeneratedColumn} from 'typeorm'

@Entity('entityname')
export class EntityName {
    @PrimaryGeneratedColumn('uuid') id: string

    @Column('varchar', { length: 500, unique: true})
    name: string

    @Column('varchar', { length: 500 })
    type: string

    @Column('numeric')
    entitynum: number
}
```

### 8. Setting up CRUD  

Import the entity created in the model using the Nest CLI:  

```
$ nest generate module entityname  // autogenerates entityname.module.ts
```

### 9. In `entityname.module.ts`  

```
import { Module } from '@nestjs/common'
import { EntitynameService } from './entityname.service'
import { EntitynameController } from './entityname.controller'
import { EntitynameEntity } from './entityname.entity'
import { TypeOrmModule } from '@nestjs/typeorm'

@Module({
    imports: [ TypeOrmModule.forFeature([ EntityName ]) ],
    controllers: [ EntitynameController ],
    providers: [ EntitynameService ]
})
export class EntitynameModule {}
```

### 10. Generate the service  

```
$ nest generate service entityname
```

### 11. Add the CRUD service to `entityname.service.ts`  

```
import { Injectable } from '@nestjs/common'
import { InjectRepository } from '@nestjs/typeorm'
import { TypeOrmCrudService } from '@nestjsx/crud-typeorm'
import { EntitynameEntity } from './entityname.entity'

@Injectable()
export class EntitynameService extends TypeOrmCrudService<EntitynameEntity> {
    constructor (@InjectRepository(EntitynameEntity) repo) {
        super(repo)
    }
}
```

### 12. Add your endpoints to your controller  

```
import { Controller} from '@nestjs/common'
import { Crud } from '@nestjsx/crud'
import { EntitynameService } from './entityname.service'
import { EntitynameEntity } from './entityname.entity'
@Crud({
    model: {
        type: EntitynameEntity
    },
    params: {
        id: {
            field: 'id',
            type: 'uuid',
            primary: true
        }
    }
})
@Controller('entityname')
export class EntitynameController {
    constructor (public service: EntitynameService) {}
}
```

This sets up the follwing endpoints:  

* GET /entityname Get all  
* GET /entityname/:id Get one by id  
* POST /entityname Add one  
* POST /entityname/bulk Add many  
* PUT /entityname/:id Replace one  
* PATCH /entityname/:id Update one  

(test the endpoints in Postman or curl)  
(optional [integration with GraphQL](https://docs.nestjs.com/))

