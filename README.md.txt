 Retos Encontrados y Soluciones

Retos y errores:
Problema: Al ejecutar las pruebas por primera vez fallaron, ya que SQLAlchemy intentaba conectarse al servidor MySQL en localhost, pero se encontraba apagado y se le denegó el acceso.
Solución: Se inicio el MySQL y al volver a hacer las pruebas ya funciono y no tuve problemas.

Manejo de Contextos de la Aplicación
Problema: Los modelos y la base de datos fallaban fuera de una petición HTTP activa.
Solución: Se implemento self.app.app_context(), selft.ctx.push(), y self.ctx.pop() dentro de los metodos detup y tearDown de cada caso de prueba para crear y limpiar las tablas de forma auslada en cada prueba. 

Validacion de rutas protegidas
Problema: Verificar que los usuarios no autenticados no pudieran acceder al catalogo de juegos.
Solucion:Mediante las peubas se comprobo que las peticiones sin secion activa hacia juegos devuelven el codigo http 302 y redirigen hacia el login para que ingresen sus datos. 


![CI](https://github.com/alondralozano5276-commits/Pruebas_unitarias_proyecto_Flask/actions/workflows/ci.yml/badge.svg)
[![Coverage](https://codecov.io/gh/alondralozano5276-commits/Pruebas_unitarias_proyecto_Flask/branch/main/graph/badge.svg)](https://codecov.io/gh/alondralozano5276-commits/Pruebas_unitarias_proyecto_Flask) 