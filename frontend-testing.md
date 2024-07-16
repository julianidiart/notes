# Frontend Testing (2021)

## Introducción

### El típico flujo de trabajo

- Flujo manual de trabajo: Escribir código, probar manualmente en el navegador, y ajustar según los resultados.

### ¿Qué es un test?

- Un proceso para obtener información sobre un sistema.
  - Ejemplo de test manual: abrir navegador, seleccionar producto, comprobar valores.

### Test automáticos vs test no automáticos

- Si los tests automáticos son fiables y rápidos, ayudan a evitar errores críticos.

### La importancia de los tests

- Tests ayudan a detectar bugs, mejorar la calidad del código y documentar la funcionalidad.
- Facilitan la mantenibilidad y extensibilidad del sistema.

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
