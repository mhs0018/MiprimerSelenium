# 🧪 Proyecto de Automatización de Login con Selenium

Este proyecto implementa pruebas automatizadas para validar el flujo de inicio de sesión en la página [SauceDemo](https://www.saucedemo.com/) utilizando **Selenium WebDriver**, **JUnit 5** y el patrón de diseño **Page Object Model (POM)**.

---

## 📁 Estructura del Proyecto

```
├──src/
│  ├── pages/
│  │   └── LoginPage.java
│  └── test/
│       └── LoginTest.java
├── .gitignore
├── pom.xml
└── README.md
```

* **pages/**: Contiene las clases que representan las páginas (Page Objects).
* **test/**: Contiene los casos de prueba automatizados.

---

## 🧩 Tecnologías utilizadas

* Java
* Selenium WebDriver
* JUnit 5
* WebDriverManager

---

## 📄 Descripción de Clases

### 🔹 LoginPage

Clase que encapsula la interacción con la página de login siguiendo el patrón POM.

Incluye:

* Localizadores (`By`)
* Métodos para interactuar con la UI
* Métodos de verificación

Ejemplo de funcionalidades:

* Ingresar usuario y contraseña
* Hacer login
* Obtener URL y título
* Validar errores

---

### 🔹 LoginTest

Clase de pruebas que valida distintos escenarios de login.

Incluye:

* Configuración y cierre del navegador
* Casos de prueba con JUnit

Casos implementados:

#### ✅ Login correcto

* Verifica que el usuario accede a la página de inventario

#### ❌ Login incorrecto

* Verifica que se muestra un mensaje de error
* Valida el contenido del mensaje

---

## 🚀 Cómo ejecutar las pruebas

1. Clonar el repositorio
2. Asegurarse de tener Java instalado
3. Ejecutar las pruebas desde tu IDE (IntelliJ, Eclipse) o con Maven/Gradle

Las pruebas abrirán automáticamente Chrome gracias a WebDriverManager.

---

## 🧪 Buenas prácticas aplicadas

* Uso de **Page Object Model (POM)** para separar lógica de UI y pruebas
* Métodos reutilizables
* Validaciones claras con mensajes descriptivos
* Manejo adecuado del ciclo de vida del driver (`@BeforeEach`, `@AfterEach`)

---

## 📸 Captura de pantalla

* Muestra que los test funcionen correctamente

<img width="1914" height="1030" alt="Captura de pantalla 2026-04-14 231121" src="https://github.com/user-attachments/assets/cd223168-528e-4fee-8286-e887ecffe7b9" />

* Los avisos que se muestran en la consola no son fallos de los test, solo indica que Selenium está una versión por detrás del navegador usado (Chrome).

---

## 📝 Cuestiones

* ¿Qué hace la anotación @BeforeEach?

Indica que ese método va a ejecutarse antes de cada test. En este proyecto, por ejemplo, se encarga de abrir el navegador, inicializar WebDriver e ir a la URL donde se van a realizar las pruebas (https://www.saucedemo.com/).


* ¿Para qué sirve assertTrue?

Es una aserción que verifica que la condición descrita sea verdadera. Si la condición es true, el test es válido, y si no, falla.


* ¿Qué diferencia hay entre findElement() y findElements()?

findElement() devuelve un solo elemento, y si no lo encuentra lanza el error NoSuchElementException. findElements() devuelve una lista de elementos, y si no los encuentra devuelve la lista vacía, no un error.


* ¿Por qué utilizamos una clase LoginPage en lugar de escribir todo en el test?

Se utuliza para aplicar el Page Object Model (POM), que separa las "responsabilidades" a la hora de automatizar pruebas, y de esta manera los test solo se encargan de verificar y la clase solo se encarga de realizar las acciones. Esto mejora la organización.

También permite reutilizar código y facilita el mantenimiento de la aplicación (ej: si hubiera que modificar una clase, los tets no se verían afectados).


---

Proyecto realizado por: María Hernández Sosa

---
