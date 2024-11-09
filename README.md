# Pruebas-API-para-Urban-Grocers- :fork_and_knife:
Urban Grocers es una aplicación de entrega de productos por catálogo y kits comestibles. El área de desarrollo agregó una nueva función en la API de Urban Grocers, así que fue necesario realizar pruebas para dos aspectos: la cantidad comestibles que se pueden agregar a un kit y comprobar si el costo del servicio de entrega Order and Go en relación al horario es correcto según los requisitos.
# Herramientas 
![Static Badge](https://img.shields.io/badge/Excel-black?style=for-the-badge&logoColor=white&color=%233CB371) ![Static Badge](https://img.shields.io/badge/Jira-%230052CC?style=for-the-badge) ![Static Badge](https://img.shields.io/badge/Postman-%23FF6C37?style=for-the-badge) ![Static Badge](https://img.shields.io/badge/C%C3%B3digos%20HTTP-%2373DC8C?style=for-the-badge) ![Static Badge](https://img.shields.io/badge/ApiDoc-%230055DA?style=for-the-badge)

# Pruebas Manuales para las funciones nuevas de Urban Grocers 
Lleve a cabo pruebas manuales por medio de solicitudes a la Api de Urban Grocers a través de Postman.
Para las pruebas funcionales sobre la cantidad de comestibles que se pueden agregar a un kit utilice el endpoint: POST /api/v1/kits/{id}/products. La solitud requería los siguientes parámetros: id y quantity:
```json
{
  "productsList": [
    {
      "id": 3,
      "quantity": 2
    }
  ]
}
```

Para cada uno de los parámetros se llevaron a cabo pruebas positivas y negativas utilizando valores límites y clases de prueba con el fin de cubrir la mayor cantidad de pruebas.
Las pruebas funcionales para validar el costo del servicio de entrega Order and Go en relación al horario  según los requisitos fueron realizadas con el endpoint: /order-and-go/v1/delivery. La solicutd requería los parámetros: deliverytime, productscount, productsweight: 
```json
{
    "deliveryTime": 23,
    "productsCount": 10,
    "productsWeight": 5
}
```
La pruebas positivas y negativas cubrieron cada parámetro del query tomando en cuenta los requisitos para delimitar los valores límite y las clases de prueba. 

:arrow_right:__Si deseas ver los casos de prueba da clic aquí:__ [Pruebas API Urban Grocers](https://docs.google.com/spreadsheets/d/1OCjp-zlPLeroSW8WfMx8laL7XVKU0KoE/edit?usp=sharing&ouid=103915261935983096380&rtpof=true&sd=true)

# Resultados 
Se realizaron 72 pruebas en total donde fueron encontrados 27 errores. Realicé reportes para cada error en Jira. Algunos de los errores encontrados más importantes fueron:

Para __la cantidad comestibles que se pueden agregar a un kit__. al realizar una solitud desde Postman,la API permite: 
-   Agregar comestibles al kit con un ID 0(inexistente). La solicutd arroja un código de respuesta 200OK en lugar de un código 400 Bad request
-   Agregar una cantidad negativa al especificar la cantidad de productos que se deben agregar al kit.  La solicutd arroja un código de respuesta 200OK en lugar de un código 400 Bad request
 
