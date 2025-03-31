## Sistema de módulos de Node.js

Node.js implementa el sistema de módulos CommonJS, donde cada archivo es tratado como un módulo independiente. Los módulos pueden exportar valores, funciones u objetos, y otros módulos pueden importarlos.


### Tipos de módulos:

* **Módulos centrales (core modules):** Integrados en Node.js (fs, http, path, etc.)

* **Módulos locales:** Archivos creados por el desarrollador

* **Módulos de terceros:** Instalados a través de npm (Express, Mongoose, etc.)

---

### Lista de módulos importantes en Node.js

#### 1. Módulo `fs` (File System)
**Explicación:** Proporciona funcionalidades para trabajar con el sistema de archivos.

```Javascript
const fs = require('fs');

// Leer un archivo
fs.readFile('archivo.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});

// Escribir en un archivo
fs.writeFile('archivo.txt', 'Contenido nuevo', (err) => {
  if (err) throw err;
});
```
#### 2. Módulo `http`

**Explicación:** Permite crear servidores HTTP.

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hola Mundo');
});

server.listen(3000, () => {
  console.log('Servidor en http://localhost:3000');
});
```

#### 3. Módulo `path`

**Explicación:** Proporciona utilidades para trabajar con rutas de archivos y directorios.

```javascript
const path = require('path');

// Unir segmentos de ruta
const fullPath = path.join(__dirname, 'carpeta', 'archivo.txt');
console.log(fullPath);

// Obtener la extensión de un archivo
const ext = path.extname('index.html');
console.log(ext); // .html
```

#### 4. Módulo `os`

**Explicación:** Proporciona utilidades relacionadas con el sistema operativo.

```javascript
const os = require('os');

console.log(os.platform()); // Sistema operativo
console.log(os.totalmem()); // Memoria total
console.log(os.freemem()); // Memoria libre
console.log(os.cpus()); // Información de CPUs
```

#### 5. Módulo `events`

**Explicación:** Proporciona funciones de utilidad.

```javascript
const util = require('util');

const sleep = util.promisify(setTimeout);

async function demo() {
  await sleep(1000);
  console.log('Después de 1 segundo');
}

demo();
```

#### 6. Módulo `util`

**Explicación:** Proporciona funciones de utilidad.

```javascript
const util = require('util');

const sleep = util.promisify(setTimeout);

async function demo() {
  await sleep(1000);
  console.log('Después de 1 segundo');
}

demo();
```

#### 7. Módulo `crypto`

**Explicación:** Proporciona funcionalidades criptográficas.

```javascript
const crypto = require('crypto');

// Crear hash
const hash = crypto.createHash('sha256');
hash.update('datos para hashear');
console.log(hash.digest('hex'));

// Generar ID único
console.log(crypto.randomUUID());
```

#### 8. Módulo `stream`

**Explicación:** Proporciona una API para trabajar con flujos de datos.

```javascript
const { Readable } = require('stream');

const miStream = new Readable({
  read(size) {
    this.push('datos\n');
    this.push(null); // Fin del stream
  }
});

miStream.pipe(process.stdout);
```

#### 9.Módulo `child_process`

**Explicación:** Permite crear procesos hijos.

```javascript
const { exec } = require('child_process');

exec('ls -la', (error, stdout, stderr) => {
  if (error) {
    console.error(`Error: ${error.message}`);
    return;
  }
  console.log(stdout);
});
```

#### 10.  Módulo `querystring`

**Explicación:** Proporciona utilidades para trabajar con cadenas de consulta URL.

```javascript
const querystring = require('querystring');

const obj = querystring.parse('nombre=Juan&edad=30');
console.log(obj); // { nombre: 'Juan', edad: '30' }

const str = querystring.stringify({ nombre: 'Juan', edad: 30 });
console.log(str); // nombre=Juan&edad=30
```
---

### Crear tus propios módulos
Puedes crear y exportar tus propios módulos:

```javascript
// modulo.js
function saludar(nombre) {
  return `Hola ${nombre}`;
}

module.exports = {
  saludar
};

// app.js
const { saludar } = require('./modulo');
console.log(saludar('Juan'));
```
O usando `exports` directamente:

```javascript
// modulo.js
exports.saludar = function(nombre) {
  return `Hola ${nombre}`;
};
```
---

### Módulos de terceros

Puedes instalar módulos de terceros usando npm:

```bash
npm install nombre-del-modulo
```
Y luego requerirlos:


```javascript
const express = require('express');
const mongoose = require('mongoose');
```