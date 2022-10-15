# Trabajo Práctico 9  

## 1

La dependencia `spring-boot-starter-test` es un starter kit con los elementos necesarios para testear aplicaciones spring.

## 2

El test case `HelloWorldServiceTest` comprueba que el método `getHelloMessage()` de la clase `HelloWorldService` devuelva el mensaje "Spring boot says hello from a Docker container"

## 3

El test crea un mock de la clase `Info.Builder` y lo usa para verificar el correcto funcionamiento del método `contribute()` de la clase `ExampleInfoContributor`.

## 4

El test:

```java
@Test
	public void myTest() {
		HelloWorldService helloWorldService = new HelloWorldService();
		assertEquals("Expected correct message","Hola Hola",helloWorldService.getHelloMessage());
		assertEquals("Expected correct message","Hello Hello",helloWorldService.getHelloMessage());
	}
```

Por otro lado, la clase `AbstractTest` es una clase abstracta que implementa el método `setUp()`, el cual prepara un mock mvc para utilizar como contexto web.

La clase `SampleControllerTest` extiende la anterior.
Crea el mock mvc antes de ejecutar los tests con indicando el método con `@Before`.
Luego chequea que el entorno esté preparado correctamente comprobando el estado recibido con el código 200 (Http Status OK).
Si todo fue bien chequea que el contenido de la respuesta sea el esperado.

## 6

Los test ya se ejecutaban durante la ejecución del build.
