# Frontend Testing (2021)

## Introducción

### El típico flujo de trabajo

- Flujo manual de trabajo: Escribir código, probar manualmente en el navegador, y ajustar según los resultados.

### ¿Qué es un test?

- Un proceso para obtener información sobre un sistema.
  - Ejemplo de test manual: abrir navegador, seleccionar producto, comprobar valores.

### Test automáticos vs test no automáticos

- Si los tests automáticos son fiables y rápidos, ayudan a evitar errores críticos.

### La importancia de los tests

#### Las excusas

- "No tengo tiempo"
  - Al principio, aprender a hacer tests puede ser costoso, pero a largo plazo ahorra tiempo y mejora la eficiencia.
- "Muchos bugs no se podrían detectar incluso haciendo tests"
  - Los tests reducen la frecuencia de errores, aunque no los eliminan por completo.
- "Mi cliente no quiere tests"
  - Una vez el equipo es productivo, ningún cliente se opondrá a una mayor productividad.
- "Mi código cambia constantemente, no tiene sentido hacer tests"
  - Los tests pueden estar demasiado acoplados al código.
  - Si los requisitos cambian, es un problema de producto, no de ingeniería.
- "Mi código no cambia nunca, no tiene sentido hacer tests"
  - El código puede no cambiar porque no tiene tests y nadie se atreve a tocarlo.
  - En el software, el cambio es constante.
- "Mi código es muy difícil de probar"
  - Hay recursos para aprender a probar código legacy.
  - Los tests ahorran tiempo y dinero, reducen bugs y permiten refactors frecuentes.

#### Beneficios principales de los tests

- Documentación
  - Los tests sirven como “documentación viva”.
  - Ayudan a entender y actualizar el código con cada nuevo requisito.
- Diseño
  - Mejoran la calidad del código al hacerlo más modular y cumplir principios SOLID.
  - Metodologías como TDD previenen código innecesario y facilitan refactors.
- Verificación
  - Permiten verificar requisitos de forma rápida y automática.
  - Reducen el coste de mantenimiento y extensibilidad del sistema.
  - A medida que el proyecto crece, las ventajas del testing se hacen evidentes.

### Entonces ¿Por donde empiezo?

- Jest es una de las librerías más populares para escribir tests en JavaScript.
  - Ejemplo de test con Jest:

```javascript
// Description
test("this is the test description", () => {
  // Arrange
  const template = "Hello <name>!";
  // Act
  const actual = template.replace("<name>", "world"); // Assert
  expect(actual).toEqual("Hello world!");
});
```

- Partes de un test:
  - Nombre o Descripción: Indica qué código estamos y qué resultado se espera.
  - Arrange: Una primera parte en la que preparamos el test.
  - Act: Una segunda parte en la que se ejecuta el código que se quiere probar.
  - Assert: Una parte final en la que se compara el resultado obtenido con el resultado esperado.

## Características de un test

### Sensibilidad: Sensible vs Insensible

- La sensibilidad indica la probabilidad de que un test falle cuando el código tiene errores.
  - Test insensible: por ejemplo, no detectará un error en el encoding de caracteres.

```javascript
test("A tweet should be displayed ok", () => {
  // Abrir la URL del tweet
  browser.open(TWEET_URL);
  // Obtener el texto del tweet
  const tweetText = browser.querySelector(".Tweet").innerText;
  // Comprobar que el texto no está vacío
  expect(tweetText).not.toEqual("");
});
```

    - Test sensible:

```javascript
test("A tweet should be displayed ok", () => {
  // Abrir la URL del tweet
  browser.open(TWEET_URL);
  // Obtener el texto del tweet
  const tweetText = browser.querySelector(".Tweet").innerText;
  // Comprobar que el texto es el esperado
  expect(tweetText).toEqual("This is a test tweet!");
});
```

### Especificidad: Específico vs Inespecífico

- La especificidad indica la capacidad de un test de dar por bueno un comportamiento correcto.
  - Test inespecífico: Comprueba sólo si la función es llamada.

```javascript
test("A tweet should be shown on a Modal", () => {
  // Crear un espía en la función "open" de la librería de popups
  const spy = jest.spyOn(popupLibrary, "open");
  // Crear un objeto tweet de prueba
  const tweet = new Tweet("This is the text of the tweet");
  // Ejecutar la función del objeto tweet que mostrará el Modal
  tweet.openInPopUp();
  // Comprobar que la función open de la librería ha sido llamada
  expect(spy).toHaveBeenCalled();
});
```

    - En el ejemplo caso sigue siendo inespecífico ya que sigue acoplado a la implementación (por ejemplo, si la librería se actualiza el método *open* pasa a llamarse *show*, el test fallaría)

```javascript
test("A tweet should be shown on a Modal", () => {
  // Crear un espía en la función "open" de la librería de popups
  const spy = jest.spyOn(popupLibrary, "open");
  // Crear un objeto tweet de prueba
  const tweet = new Tweet("This is the text of the tweet");
  // Ejecutar la función del objeto tweet que mostrará el Modal
  tweet.openInPopUp();
  // Comprobar que la función open ha sido llamada correctamente
  expect(spy).toHaveBeenCalledWith(tweet.getText());
});
```

### Flexibilidad: Flexible vs Inflexible

- La flexibilidad indica la tolerancia que tiene un test ante los cambios en el código.
  - Test inflexible: acoplado a una implementación, cambios en el código que no alteran el correcto funcionamiento final de la aplicación pueden dar lugar a falsos positivos.
  - En el siguiente ejemplo, si se cambia el div por un span, el test falla, sin embargo lo que ven los usuarios _puede_ no verse afectado, generando un falso positivo.

```javascript
test("should display a popup", () => {
  // ... Omitimos el resto del test
  const actual = popup.innerHTML;
  // Comprobamos que el HTML es el esperado
  expect(actual).toEqual(
    <div class="Info">Los cambios se han guardado con éxito.</div>
  );
});
```

    - Test flexible:

```javascript
test("should display a popup", () => {
  // ... Omitimos el resto del test
  const actual = screen.queryByText("Los cambios se han guardado con éxito.");
  expect(actual).toBeVisible();
});
```

### Estabilidad: Estable vs Inestable

- La estabilidad indica si el resultado del test depende de factores externos (flaky tests).
  - Test inestable: El test depende de un factor externo (la fecha depende del momento en el que se corra el test).

```javascript
test("date.toGMTString() should return a be properly formatted date", () => {
  const actual = new Date().toGMTString();
  expect(actual).toEqual("Fri, 20 Mar 2020 22:00:00 GMT");
});
```

    - Test estable: El test es más estable, pero sigue dependiendo de la máquina donde se ejecute el test, por ejemplo, si el idioma no es Inglés, el locale que devuelva será distinto y el test fallará.

```javascript
test("date.toGMTString() should return a be properly formatted date", () => {
  // Especificamos una fecha concreta
  new Date(2020, 2, 20, 23, 0, 0, 0).toGMTString();
  expect(actual).toEqual("Fri, 20 Mar 2020 22:00:00 GMT");
});
```

### Precisión: Preciso vs Impreciso

- La precisión indica la capacidad que tiene un test de indicar el origen de los fallos.
- Cuando un test muy preciso falla se sabe perfectamente donde está la fuente del error mientras que cuando un test impreciso falla es necesario perder tiempo depurando código para encontrar el fallo.

### Mantenibilidad: Mantenible vs Inmantenible

- La mantenibilidad indica lo fácil que es para los desarrolladores hacer cambios en un test y mantenerlos actualizados.
- Los test forman parte de la báse de código y deben ser tratados como tal.

### Velocidad: Velóz vs Lento

- La velocidad nos indica cuanto tiempo require un test para ejecutarse.

### Profundidad: Profundo vs Superficial

- La profundidad nos indica cuantas dependencias se ejecutan en un test.
  - Test superficial: Sustituye las dependencias por test-dobles con un comportamiento conocido.

```javascript
// Se importan los 3 módulos
import A from "./A";
import B from "./B";
import C from "./C";
test("...", () => {
  // Sustituir módulo B por un mock jest.spyOn(B).mockImplementation(...); // Sustituir módulo C por un mock jest.spyOn(C).mockImplementation(...); // Probar A
  expect(A).toDoSomething();
});
```

    - Test profundo: Prueba el código de un módulo junto con el de sus dependencias.

```javascript
// Se importa A
import A from "./A";
test("...", () => {
  // Se prueba A, y con ello todas sus dependencias expect(A).toDoSomething();
});
```

## Tipos de Tests

### Small | Unidad

- Rápidos de ejecutar.
- Muy precisos: al fallar, se sabe exactamente dónde está el error.
- Escriben los programadores para validar la lógica de bajo nivel.
- Profundidad cero (sin dependencias).

### Medium | Integración

- Prueban la interacción de unidades independientes.
- Verifican que las unidades colaboran correctamente.
- Pueden duplicar pruebas de tests unitarios para asegurar sensibilidad y cobertura.

### Medium | Funcional

- Tests de integración de alto nivel.
- Pueden introducir inestabilidad.
- En frontend, prueban la interacción del cliente JavaScript con una API.

### Large | End-to-End | System

- Prueban el sistema completo desde el principio hasta el final.
- Recrean condiciones reales de producción.
- Son lentos e inestables, y se limitan a casos de uso básicos.

## Cómo distribuir los tests

- Los tests deben ser útiles, no solo escritos por compromiso o para alcanzar un porcentaje de cobertura.
- Pensar en el "qué" antes que el "cómo".
- Los tests deben parecerse lo máximo posible al entorno de producción, limitando el uso de test dobles y enfocándose en la funcionalidad.

### Pirámide del testing

- Minimizar la cantidad de tests inestables, imprecisos y lentos, y maximizar los tests estables, precisos y rápidos.

- Base: Tests unitarios (más importantes y en mayor cantidad).
- Siguiente nivel: Tests de integración.
- Nivel superior: Tests funcionales.
- Cima: Tests E2E .

### Trofeo del testing

- Los tests unitarios sociables (integración según Fowler) están más cerca en el trofeo.
- Evitar el uso excesivo de test dobles y simular fielmente el comportamiento del usuario.

- Base: Analizadores estáticos (herramientas que leen el código sin ejecutarlo y buscan errores comunes).
- Siguiente nivel: Tests unitarios.
- Siguiente nivel (más importante y mas cantidad): Test de integración.
- Siguiente nivel: E2E.

### El barco del testing

- Combina la pirámide y el trofeo del testing.

- Quilla: Analizadores estáticos (Eslint, Typescript).
- Cubierta inferior: Tests unitarios.
- Cubierta media: Tests de integración (testing-library).
- Cubierta superior: Tests E2E (Cypress).
- Complementarios: Pruebas de contratos, UI y accesibilidad.

## Ejemplos de frontend testing

## Otros tipos de testing

### E2E Testing

- Pruebas de principio a fin que reproducen las condiciones reales de producción.
- Lentas y frágiles debido a fallos de red y cambios en los selectores.
- Herramientas:
  - Cypress.io
  - Selenium

### Visual Regression Testing

- Compara capturas de pantalla para detectar cambios en la apariencia de la aplicación.
- Alta fragilidad debido a diferencias sutiles entre sistemas operativos y navegadores.
- Herramientas:
  - BackstopJS
  - Chromatic

### API Testing

- Garantiza la compatibilidad entre cliente y servidor.
- Herramientas:
  - Postman

### Contract Testing

- Asegurar que los cambios en la API no rompan el contrato entre cliente y servidor.
- Herramientas:
  - Pact

### Snapshot Testing

- Técnica para comprobar que no se introducen cambios inesperados en la interfaz.

### Property Based Testing

- Prueba propiedades de funciones con entradas generadas automáticamente.
- Herramientas:
  - JSVerify

### Performance Testing

- Detecta problemas de rendimiento en aplicaciones web.
- Herramientas:
  - Lighthouse

### Manual Testing

- Pruebas realizadas manualmente, probando diferentes situaciones.

## Testing doubles

- Los testing doubles son objetos que sustituyen a los reales en un entorno de prueba, emulando sus características o comportándose de manera esperada.
- Pueden ser útiles, es recomendable limitar su uso.

### Dummy

- Objetos que rellenan huecos para ejecutar el test, pero no se utilizan ni afectan la lógica del test.
- Ejemplo:

```javascript
describe("validateUserEmail", () => {
  it("should return true when the email is valid", async () => {
    const dummyUsername = "dummy_username"; // <--- valor no importante
    const validEmail = "valid@mail.com";
    const user = new User(dummyUsername, validEmail);
    const actual = validateUserEmail(user);
    expect(actual).toEqual(true);
  });

  it("should return false when the email is not valid", async () => {
    const dummyUsername = "dummy_username"; // <--- valor no importante
    const invalidEmail = "invalid_email";
    const user = new User(dummyUsername, invalidEmail);
    const actual = validateUserEmail(user);
    expect(actual).toEqual(false);
  });
});
```

### Stub

- Dummies con un comportamiento predefinido.
  - Ejemplo:

```javascript
describe('.buyItem(Item)', () => {
  it('should contain an ok message when the payment is ok', async () => {
    jest.spyOn(paymentService, 'pay').mockResolveValue({ errorCode: null });
    const item = createItem(...);
    const actual = await buyItem(item);
    expect(actual.userMsg).toEqual('Payment was ok!');
  });

  it('should contain a user-friendly message when the card is expired', async () => {
    jest.spyOn(paymentService, 'pay').mockResolveValue({ errorCode: '123' });
    const item = createItem(...);
    const actual = await buyItem(item);
    expect(actual.userMsg).toEqual('The card has expired. Check the expiration date or use a different card.');
  });
});
```

### Spy

- Stubs que almacenan información sobre cómo han sido utilizados.

```javascript
describe("displayNotification", () => {
  test("should show a popup with the right text when the popup flag is true", () => {
    const spy = jest.spyOn(notificationLibrary, "displayPopup");
    const notification = { isPopup: true, text: "dummy_text_1" };
    displayNotification(notification);
    expect(spy).toHaveBeenCalledWith(notification.text);
  });

  test("should show an alert with the right text when the popup flag is false", () => {
    const spy = jest.spyOn(notificationLibrary, "alert");
    const notification = { isPopup: false, text: "dummy_text_2" };
    displayNotification(notification);
    expect(spy).toHaveBeenCalledWith(notification.text);
  });
});
```

### Fake

- Objetos con implementación real pero no usable en producción.

### Mock

- Incluye comprobaciones preprogramadas sobre las interacciones esperadas.
  - Ejemplo:

```javascript
const myMock = jest.fn().mockImplementation(() => {
  return {
    method: jest.fn().mockReturnValue(true),
  };
});

const mockInstance = myMock();
mockInstance.method();
expect(mockInstance.method).toHaveBeenCalled();
expect(mockInstance.method).toHaveReturnedWith(true);
```

## Buenas prácticas en Testing

### SWA: Should, When, And

1. Indicar el requisito que se está probando: Sirve como documentación sobre el comportamiento esperado del sistema.
   - Ejemplo:

```javascript
test('should validate user email', () => { ... });
```

2. Indicar el estado inicial y el resultado esperado: Define el punto de partida y el resultado esperado del test.
   - Ejemplo:

```javascript
test('should return true when email is valid', () => { ... });
```

3. Indicar claramente la unidad que se está probando: Ayuda a identificar qué pieza de código contiene el error cuando un test falla.
   - Ejemplo:

```javascript
describe('.validateUserEmail(user)', () => { ... });
```

- Ejemplo completo:

```javascript
describe(".showPopup(data)", () => {
  describe("when a message is passed", () => {
    describe("and it has a title", () => {
      test("should display the title", () => {});
      test("should display the message", () => {});
    });
    describe("and it doesn't have a title", () => {
      test("should hide the title", () => {});
      test("should display the message", () => {});
    });
  });
  describe("when no message is passed", () => {
    describe("and it has a title", () => {
      test("should display the title", () => {});
      test("should hide the message", () => {});
    });
    describe("and it doesn't have a title", () => {
      test("should throw an error", () => {});
    });
  });
});
```

### Partes de un test (AAA)

1. Arrange: Prepara el estado inicial del sistema.
   - Ejemplo:

```javascript
const dummyUser = { isVip: false };
```

2. Act: Ejecuta el código que se va a probar.
   - Ejemplo:

```javascript
const actual = hasFreeTickets(dummyUser);
```

3. Assert: Verifica que el resultado es el esperado.
   - Ejemplo:

```javascript
expect(actual).toBe(false);
```

### Un test solo debería fallar por una razón

- Dividir tests en unidades pequeñas.
- Evita probar múltiples cosas en un solo test.
- Ejemplo:

```javascript
describe(".getBook(bookID: string)", () => {
  test("should return the right book", () => {
    const actual = bookApi.getBook("fake_book_id");
    expect(actual).toBe(expected);
  });

  test("should mark the book as taken", () => {
    const actual = bookApi.getBook("fake_book_id");
    expect(bookApi.isTaken("fake_book_id")).toBe(true);
  });
});
```

### No incluir lógica en el test

- Evitar complejidad innecesaria
- Ejemplo:

```javascript
describe("urlService.getAvatar(user)", () => {
  test("should return a valid avatar url", () => {
    const actual = urlService.getAvatar(user, "https://cdn.example.com/");
    expect(actual).toEqual(
      "https://cdn.example.com/photos/avatar/dummie_user_id"
    );
  });
});
```

### No probar la implementación

- Probar la funcionalidad esperada, no la implementación.
- Ejemplo:

```javascript
describe("Calculator", () => {
  describe(".add(a: number, b: number)", () => {
    test("should add two numbers", () => {
      const calculator = new Calculator();
      const actual = calculator.add(1, 3);
      expect(actual).toBe(4);
    });
  });
});
```

### No probar métodos privados

- Probar métodos públicos que utilizan métodos privados.
- Refactorizar métodos privados complejos en unidades separadas.

### Probar comportamiento en lugar de estado

- Basado en la simulación de interacciones de usuarios.

### Exportar Servicios

- Agrupar y exportar funciones puras.
- Facilita la prueba y sustitución por test doubles.

### No confiar ciegamente en la cobertura

- La cobertura es orientativa, no definitiva.
- Escribir tests para todos los posibles casos de uso.
- Probar con elementos de cada clase de equivalencia
