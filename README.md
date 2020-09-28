# mercantil
pruebas de mercantil


Challenge QA Automation Mercantil

Instrucciones:
- El challenge se compone de 2 partes, por un lado, realizar un test a nivel API (Backend) y
por otro, un test a nivel Frontend.
- El lenguaje de programación puede ser Java, Python, u otro
- Para el caso de frontend, utilizar Selenium WebDriver.
- Preferentemente utilizar: Maven, IntelliJ IDEA, Karate
- Se permitirá solo el uso de herramientas de tipo openSource.
- Se deberá proveer todo lo necesario para la ejecución del test como comandos, doc de
referencia, consideraciones, etc.
-Luego de realizar los test, subir el código a un Bitbucket personal público.
Test Frontend:
1- Generar una clase, con un método de test que instancie un chromedriver.
2- Ingrese a la home de Mercantil (https://www.mercantilandina.com.ar/).
3- Seleccionar “Seguros".
4- Seleccionar “Hogar”
5-Hacer click en “Cotizar”
6- Completar campos y hacer click en Cotizar
6- Guarde la grilla de resultados como lista de WebElement y aserte que:
- Cada uno de los elementos contenga “Seguro de hogar - Mercantil andina" en su title.
-Validar que el costo mensual sea un valor positivo, mayor a cero y entero
- Validar que se visualice "Chat Online"
El test debe heredar de una clase base (TestBase) donde deben estar los annotation
@BeforeTest y @AfterTest.
Es deseable utilizar el patrón "Page Object" para el modelado de las páginas.
Test Backend:
1- Obtener una lista de cervecerías que contengan el texto "lagunitas" en su nombre.
Para ello, se debe ejecutar el siguiente servicio, indicando el texto a buscar en el
queryParam "query".
GET - https://api.openbrewerydb.org/breweries/autocomplete
2- De la lista de resultados del punto 1, tomar aquellos que contengan en la key "name", el
valor "Lagunitas Brewing Co".
3- A través del siguiente servicio, obtener el detalle de cada cervecería de la lista del punto
2 y tomar solo el que contenga
"state" = "California".
GET - https://api.openbrewerydb.org/breweries/{id}
4-Sobre la cervecería resultante, assertar lo siguiente:
"id" = 761
"name" = "Lagunitas Brewing Co"
"street" = "1280 N McDowell Blvd"
"phone" = "7077694495"

5-(Opcional) - Generar reporte con resultado de ejecución del test.
