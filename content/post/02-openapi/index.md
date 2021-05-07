---
authors:
- blogferran
date: "2021-05-07"
diagram: false
tags:
- OpenAPI
title: Generar una SDK con Swagger Codegen
subtitle: Cómo importar una client SDK para una API definida con la especificación OpenAPI
---

![png](./openapi-logo3.png)

OpenAPI nació dentro de marco de herramientas Swagger, creado para diseñar, construir, documentar y consumir REST API. Más adelante, se convirtió en un proyecto separado de colaboración de código abierto de la Fundación Linux.


La especificación OpenAPI es un formato de descripción de API para servicios web RESTful. La especificación puede estar escrita en archivos YAML o JSON, lo cual quiere decir que es independiente del lenguaje.  Estos archivos permiten describir la totalidad de la API: endpoints, parámetros, autenticación e información adicional.


Una de las grandes ventajas de las aplicaciones basadas en esta especificación es que a partir de ellas se puede generar automáticamente tanto documentación interactiva como client SDKs. 

![png](./SWC-logo-clr.png)

Con la herramienta open-source Swagger Codegen es posible generar código cliente para consumir una REST API de forma muy sencilla. Para un proyecto maven (y por extensión Spring Boot) basta con añadir la dependencia  y el plugin de Swagger Codegen al archivo pom.xml y copiar el archivo de descripción de la API en la carpeta “/resources” del proyecto.

    <dependency>
      <groupId>io.swagger</groupId>
      <artifactId>swagger-codegen-maven-plugin</artifactId>
      <version>2.4.19</version>
    </dependency>
    
    <build>
      <plugins>
        <plugin>
          <groupId>io.swagger</groupId>
          <artifactId>swagger-codegen-maven-plugin</artifactId>
          <version>2.3.1</version>
          <executions>
            <execution>
              <goals>
                <goal>generate</goal>
              </goals>
            <configuration>
              <inputSpec>${project.basedir}/src/main/resources/api.yaml</inputSpec>
              <language>java</language>
              <configOptions>
                 <sourceFolder>src/gen/java/main</sourceFolder>
              </configOptions>
            </configuration>
            </execution>
          </executions>
        </plugin>
      </plugins>
    </bluid>


Después de compilar de nuevo el proyecto, se generará el código. Toda la información se puede encontrar en la página de [Swagger](https://swagger.io) y en en el repositorio de [Codegen](https://github.com/swagger-api/swagger-codegen).
