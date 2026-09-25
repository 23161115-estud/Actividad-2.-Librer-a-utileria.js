# utileria.js

## Portada

**utileria.js** es una librería de JavaScript puro (sin frameworks, sin componentes visuales) con 8 funciones reutilizables para resolver problemas comunes en formularios web:

- Validar que un correo electrónico tenga un formato correcto.
- Validar que un campo de texto contenga solo letras.
- Validar que un número no exceda una cantidad máxima de dígitos.
- Calcular la edad exacta de una persona a partir de su fecha de nacimiento.
- Verificar si alguien es mayor de edad.
- Validar que una contraseña cumpla requisitos mínimos de seguridad.
- Normalizar texto a formato "Título".
- Calcular cuántos días faltan para una fecha objetivo.

El problema que resuelve: evitar reescribir la misma lógica de validación en cada formulario del sitio, centralizándola en un único archivo reutilizable, documentado y fácil de integrar.


---

## Instalación

No requiere ningún gestor de paquetes ni build. Solo agrega el script antes de tu propio código:

```html
<script src="js/utileria.js"></script>
```

Al cargarse, todas las funciones quedan disponibles globalmente en tu página — puedes llamarlas directamente desde cualquier otro `<script>` o archivo `.js` que se cargue después.

---

## Uso

### 1. `validarCorreo(correo)`

Valida que un correo electrónico tenga un formato correcto.

```javascript
validarCorreo("sanchi.perez@example.com"); // R: true
validarCorreo("correo-invalido");   // R: false     
```

### 2. `soloLetras(texto)`

Valida que un texto contenga solo letras (mayúsculas, minúsculas, vocales acentuadas y ñ). Permite espacios, pensado para nombres completos.

```javascript
soloLetras("María José Pérez"); // R: true
soloLetras("Juan123");  // R: false        
```

### 3. `validarLongitud(numero, maxLongitud)`

Valida que la cantidad de dígitos de un número no exceda un máximo.

```javascript
validarLongitud(4421367890, 10); // R: true
validarLongitud(44213678901, 10); // R: false
```

### 4. `calcularEdad(fechaNacimiento)`

Calcula la edad en años cumplidos a partir de una fecha de nacimiento.

```javascript
calcularEdad("2000-05-14"); 
```

### 5. `esMayorDeEdad(fechaNacimiento)`

Determina si una persona es mayor de edad (18+).

```javascript
esMayorDeEdad("2000-05-14"); // R: true
esMayorDeEdad("2015-01-01"); // R: false
```

### 6. `validarPassword(password)`

Valida que una contraseña tenga mayúscula, minúscula, número, carácter especial y mínimo 8 caracteres.

```javascript
validarPassword("Segura#2024"); // R: true
validarPassword("segura");      // R: false
```

### 7. `capitalizarTexto(texto)` — función extra

Normaliza un texto a formato "Título" (primera letra de cada palabra en mayúscula).

```javascript
capitalizarTexto("mARIA josé PÉREZ"); // R: "Maria José Pérez"
```

### 8. `calcularDiasRestantes(fechaObjetivo)` — función extra

Calcula cuántos días faltan para una fecha objetivo.

```javascript
calcularDiasRestantes("2026-12-25"); // depende de la fecha actual
```

---

## Estructura del repositorio

```
/utileria
├── README.md
├── index.html      → Formulario con las 6 validaciones obligatorias + modal de edad
├── login.html       → Login que usa validarCorreo() y validarPassword()
├── css/
│   └── styles.css
├── js/
│   └── utileria.js  → La librería
└── img/
```


## Capturas de pantalla

**Formulario de registro (`index.html`)** — usa las 6 validaciones obligatorias:

![Formulario de registro](img/Captura%20de%20pantalla%20formulario.png)

**Resultado del formulario **:

![Resultado del formulario](img/Captura%20de%20pantalla.png)

**Login (`login.html`)** — usa `validarCorreo()` y `validarPassword()`:

![Login](img/Captura%20de%20pantalla1.png)

**Funciones extra** — `capitalizarTexto()` y `calcularDiasRestantes()`:

![Funciones extra](img/Captura%20de%20pantalla%20extra.png)



---

## Video demo

https://drive.google.com/file/d/1E-_ZnL72V12BRJudfjtwlcLfHFsHX8sx/view?usp=sharing&t=6.762

---

## Autor

Ruiz Durán Emiliano