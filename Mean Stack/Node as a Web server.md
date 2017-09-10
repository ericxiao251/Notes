# Node as a Web Server

How to export/import functions, variables from another javascript file.

`config.js`:
```javascript
export const...
export func...
```
`otherflie.js`:
```javascript
import config from config;
```
---
How to create a server using the core `http` and `https` modules. As the requirement for handling a request grows, using the core module on its own would be a lot of boiler plate code that can be extracted into a framework. A popular framework is `Express JS`.
```javascript
import https from 'https';

https.get(...);
```

```javascript
import http from 'https';

const server = http.createServer((req, res)) => {
  ...
});
```

Equivalent code using `Express`.

```javascript
import express from 'express';

const server = express();

server.get('/', (req, res) => {
  res.send('Hello Express');
});

server.listen(config.port, () => {
  console.info('Express listening on port', config.port);
});
```
---
Creating and using routes with `Express`.

`api/index.js`:
```javascript
import express from 'express';

const router = express.Router();

router.get('/', (req, res) => {
  res.send({ data: [] });
});

export default router;
```

```javascript
import apiRouter from './api';

server.use('/api', apiRouter);
server.use(express.static('public'));
```

---
Use `ejs` to render dynamic html. `EJS` can also use partials.
```javascript
server.set('view engine', 'ejs');

server.get('/', (req, res) => {
  res.render('index', {
    content: '...'
  });
});
```
