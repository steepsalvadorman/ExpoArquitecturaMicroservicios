# Arquitectura de Microservicios

### Requerimientos
- Java 11+
- node 14+
- visual studio code 
- InteliJ IDEA


### Descripcion del caso practico:

Se diseñaron 2 microservicios, mscategory ( Escrito en NodeJS ) y msproduct ( Escrito en Java Spring Boot ), estos servicios se registran en un servidor Eureka lo que permite su descubrimiento mutuo y comunicacion, segun el diagrama de arquitectura basica de microservicios.

![](./recursos/example.png)



## Despliegue :
Tenemos que levantar 3 aplicaciones 
1. ms-product (java - spring boot - eureka client )
2. ms-category (nodejs - expressjs - simple eureka js)
3. eureka server ( java - eureka servidor)

#### Eureka-server
1. Abrimos el proyecto en intellij idea
2. Instalamos las dependecias de gradle

![Eureka Server IDE](./recursos/1.png)

3. Ejecutamos el proyecto (tener cuidado con el puerto **8761**)
4. Vamos a nuestro navegador favorito y abrimos http://127.0.0.1:8761

![Luego de ejecutarlo nos quedara asi](./recursos/start2.png)

5. Como podemos ver no tenemos ninguna aplicacion registrada

<br/>

#### ms-product
1. Abrimos el proyecto en intellij idea
2. Instalamos las dependecias de gradle
3. Ejecutamos el proyecto (tener cuidado con el puerto **8081**)
4. Vamos a nuestro navegador favorito y abrimos http://127.0.0.1:8081/ping

![Vemos que el servicio esta corriendo](./recursos/ms-product-ping.png)


#### ms-category
1. Abrimos el proyecto en visual studio code
2. Instalamos las dependecias de node
3. Ejecutamos el proyecto (tener cuidado con el puerto **3000**)
4. Vamos a nuestro navegador favorito y abrimos http://127.0.0.1:3000/ping

![Vemos que el servicio esta corriendo](./recursos/ms-category-ping.png)


### Ejecucion completa
Luego de completar ejecutar los proyectos podemos observar lo siguiente

1. Los servicios ejecutados se han registrado en nuextro EUREKA SERVER MS-PRODUCT - MS-CATEGORY

![Podemos ver los serivcios registrados](./recursos/end3.png)

2. Si vamos a esta url http://127.0.0.1:8081/products/categories/ping vamos a ver como podemos traer la respuerta del microservicio categoria  atraves del microservicios productos

![Hacemos ping a categorias desde productos](./recursos/ms-product-category-ping.png)

4. Vamos a traer el detalle de una categoria desde el microservicio de productos http://127.0.0.1:8081/products/categories/1

![Consultamos una categoriua atravez de productos](./recursos/ms-product-category-id.png)

5. Vamos a traer el detalle de una categoria desde el microservicio de categorias http://127.0.0.1:3000/categories/1

![Traemos el detalle de una categoria](./recursos/ms-category-id.png)
<br/>

### Reflexion:
**La idea es monstrar como funciona el services registry usando EUREKA SERVER y tambien 
la comunicacion de microservicios sin perder el poder de escalamiento haciendo una comunicacion dinamica entre microservicios.**
<br/>