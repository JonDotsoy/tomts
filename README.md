# TOM Framework

> **🚧 PROJECT ON DRAFT**

TOM is a framework for building scalable NodeJS applications based on the cleaner JS syntax, without decorators or sugar syntax.

TOM works only with classes that read their arguments and with them create an object based on this primary class.

## Usage

For example, the next App class is used to bootstrap the app.

```ts
// ./app.ts
export class APP {}
```

Now can create an instance with the TOM module.

```ts
// ./index.ts
import { createContext } from "tomts"
import { App } from "./app"

const app = createContext().factory(App)
```

Now go to write a service to its app and declare the use of its service in the App class.

```ts
// ./cat.service.ts
export class CatService {}
```

```ts
// ./app.ts
import { CatService } from "./cat.service"

export class APP {
  constructor(readonly catService: CatService) {}
}
```

Result is

```ts
App { catService: CatService {} }
```

## Features

- Support to read TS Modules
- (Coming soon) Support to read JS Modules
