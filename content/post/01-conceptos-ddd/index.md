---
authors:
- blogferran
date: "2021-04-16"
diagram: true
tags:
- DDD
title: Descubriendo conceptos nuevos
---

Poco a poco, a partir de la revisión del código del proyecto Huella Positiva y de buscar información, estoy descubriendo algunos conceptos del domain-driven design (DDD). Escribo “algunos” no porque conozca ya bastantes, sino al contrario. Me cuesta entender la idea del diseño DDD. Es por eso que intento centrarme en identificar partes del código y entender su funcionamiento para poco a poco intentar conocer mejor la idea general del DDD. 
Un par de estos conceptos: 


- Value Objects: el nombre es auto-explicativo, pero en un primer momento no entendí qué función tenían. Son objetos que tienen significado de negocio y nos sirven para modelar propiedades en las clases del dominio. El valor de estos objetos es importante y debe ser inmutable. Algunos ejemplos pueden ser el de crear un objeto EmailAdress en vez de guardar la dirección de correo como una cadena o el de crear un enumerado con los posibles roles de una entidad.


- Actions: son clases de servicio del dominio específicas que encapsulan la lógica de negocio mínima que se expone para una acción determinada. Estas clases se utilizan conjuntamente con dtos que también minimizan la transacción de información.
