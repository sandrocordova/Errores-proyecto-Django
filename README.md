# Errores-proyecto-Django
Este repositorio contiene una serie de errores encontrados en el desarrollo de un proyecto en django

ERROR
not enough arguments for format string
not enough arguments for format string python sql Django
no hay suficientes argumentos para la cadena de formato

![WhatsApp Image 2022-07-26 at 2 36 03 PM](https://user-images.githubusercontent.com/33694187/181369499-776d0117-ef6d-40b4-8709-a0cb4e7297fc.jpeg)

SOLUCIÓN
Para este error en específico el problema es la sintaxis de Django con la BDD (SQL server).
El script enviado a la BDD contiene:

  and om.OPME_DESCRIPCION like '%WEB%' AND PF.VENT_CODIGO like '%8%'
  
En el script enviado a la BDD se encuentran símbolos como “%” que hacen referencia a la búsqueda de una 
palabra o número dentro de un registro de la base de datos. Estos símbolos son también símbolos
reservados de Django por lo que ocurre un choque entre Django y la BDD. Después en la documentación de 
PYODBC se encontró que la solución es hacer un doble “%%” haciendo referencia al símbolo “%” pero de tal 
forma que lo entienda Django. Entonces, el script final será el siguiente
