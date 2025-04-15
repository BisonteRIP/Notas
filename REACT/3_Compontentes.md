## Componentes en React: Explicación con Ejemplos y Sintaxis

Los componentes son los bloques fundamentales de cualquier aplicación React. Permiten dividir la UI en piezas independientes y reutilizables.

---

#### Tipos de componenetes

* **Componentes Funcionales (Recomendados)**
```jsx
// Componente funcional básico
function Saludo(props) {
  return <h1>Hola, {props.nombre}</h1>;
}

// Versión con desestructuración de props
function Saludo({ nombre }) {
  return <h1>Hola, {nombre}</h1>;
}

// Uso
<Saludo nombre="Ana" />

```

* **Componentes de Clase (Legacy)**
```jsx
class Saludo extends React.Component {
  render() {
    return <h1>Hola, {this.props.nombre}</h1>;
  }
}

// Uso
<Saludo nombre="Carlos" />
```
* **Componentes con Estado (useState)**
```jsx
import { useState } from 'react';

function Contador() {
  const [count, setCount] = useState(0); // Estado inicial: 0

  return (
    <div>
      <p>Contador: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Incrementar
      </button>
    </div>
  );
}
```

* **Componentes con Props**

```jsx
function TarjetaUsuario({ nombre, edad, foto }) {
  return (
    <div className="tarjeta">
      <img src={foto} alt={nombre} />
      <h2>{nombre}</h2>
      <p>Edad: {edad}</p>
    </div>
  );
}

// Uso
<TarjetaUsuario 
  nombre="María" 
  edad={25} 
  foto="/maria.jpg" 
/>
```

* **Componentes con Children**
```jsx
function Caja({ children }) {
  return <div className="caja-estilo">{children}</div>;
}

// Uso
<Caja>
  <h2>Título</h2>
  <p>Contenido aquí...</p>
</Caja>
```

* **Buenas Prácticas**

1. **Nombres en PascalCase:** MiComponente (no miComponente)

2. **Un componente por archivo:** Button.jsx, Navbar.jsx

3. **Props inmutables:** No modificar las props recibidas

4. **Separar lógica y presentación:** Componentes "tontos" (UI) y "contenedores" (lógica)

