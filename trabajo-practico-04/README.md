# Resolución TP 4

## 1

El sistema consiste de 15 microservicios cargados en 15 contenedores diferentes. Estos son:

  * front-end
  * edge-router
  * catalogue
  * catalogue-db
  * carts
  * carts-db
  * orders
  * orders-db
  * shipping
  * queue-master
  * rabbitmq
  * payment
  * user
  * user-db
  * user-sim

El único entrypoint es edge-router. Que publica los puertos 80 y 8080.

## 3

Se utilizan repositorios separados para seguir la arquitectura de microservicios. Esto permite una mayor tolerancia a fallos, desacomplamiento y facilidad de testeo.
Un punto en contra es la complejidad para el desarrollo y la coordinación entre los distintos microservicios.

## 4

El container front-end funciona como API Gateway.

## 5, 6

El servicio **user** procesa esa operación

## 7

El servicio **catalogue** responde a *localhost/catalogue* y a *localhost/tags*

## 8

Los servicios que necesitan persistir datos se conectan con una base de datos MongoDB que utilizan con este propósito. Estos son:

  * catalogue-db
  * carts-db
  * orders-db
  * user-db

## 9

El servicio encargado de la cola de mensajes es **queue-master**
