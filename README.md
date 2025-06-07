# 📚 UserListAppJava — Consumo de API REST en Android

## 📖 Índice

1. [Introducción](#introducción)
2. [¿Qué es JSONPlaceholder?](#qué-es-jsonplaceholder)
3. [Tecnologías Usadas](#tecnologías-usadas)
4. [Objetivos del Proyecto](#objetivos-del-proyecto)
5. [¿Qué Hace la App?](#qué-hace-la-app)
6. [Vista de la App](#vista-de-la-app)
7. [Estructura del Proyecto](#estructura-del-proyecto)
8. [Explicación de Cada Archivo](#explicación-de-cada-archivo)
9. [¿De Dónde se Consume la API?](#de-dónde-se-consume-la-api)
10. [¿Por Qué Trae Esta Información?](#por-qué-trae-esta-información)
11. [Flujo de Datos](#flujo-de-datos)

## ✨ Introducción

**UserListAppJava** es una aplicación móvil desarrollada en **Java** para **Android** que demuestra cómo **consumir un API REST** de manera sencilla y eficiente usando tecnologías modernas como **Retrofit** y **Gson**.

La aplicación conecta a un servicio web de prueba (**JSONPlaceholder**) para descargar y mostrar en tiempo real una lista de usuarios ficticios en un formato de lista desplazable utilizando **RecyclerView**.

## 🌐 ¿Qué es JSONPlaceholder?

**JSONPlaceholder** es un **API pública falsa** (mock API) muy usada por desarrolladores para:
- Simular peticiones reales sin necesidad de tener un servidor propio.
- Hacer peticiones HTTP como `GET`, `POST`, `PUT`, `DELETE`.

🔗 En este proyecto usamos el **endpoint**:

```
https://jsonplaceholder.typicode.com/users
```

que devuelve un listado de usuarios ficticios en formato **JSON** como:

```json
[
  {
    "id": 1,
    "name": "Leanne Graham",
    "email": "Sincere@april.biz"
  },
  {
    "id": 2,
    "name": "Ervin Howell",
    "email": "Shanna@melissa.tv"
  }
]
```

## 🛠️ Tecnologías Usadas

| Tecnología         | Uso                                                   |
|--------------------|-------------------------------------------------------|
| **Java**            | Lenguaje de programación principal                   |
| **Android SDK**     | Framework para construir apps Android                |
| **Retrofit**        | Cliente HTTP para Android (consumo de APIs REST)      |
| **Gson**            | Conversión automática de JSON a objetos Java         |
| **RecyclerView**    | Componente eficiente para mostrar listas dinámicas   |
| **JSONPlaceholder** | API gratuita para pruebas de consumo de usuarios     |

## 🎯 Objetivos del Proyecto

- Entender cómo consumir una **API REST** desde una app Android.
- Aprender a convertir respuestas **JSON** en clases de modelo **Java**.
- Mostrar información en una lista interactiva (**RecyclerView**).
- Practicar el uso de herramientas modernas como **Retrofit** y **Gson**.
- Construir una **arquitectura limpia, modular y escalable**.

## 🔍 ¿Qué Hace Exactamente la App?

- Se conecta automáticamente a la **API REST** al abrirse.
- Descarga una **lista de usuarios** (nombre y correo).
- Muestra estos usuarios en una **lista desplazable** usando **RecyclerView**.
- Los datos son **cargados dinámicamente** desde Internet.
- Funciona en **cualquier emulador** o **dispositivo Android real**.

## 🖼️ Vista de la App

📱 Lo que verás en pantalla:

| Nombre             | Email                |
|--------------------|----------------------|
| Leanne Graham      | Sincere@april.biz     |
| Ervin Howell       | Shanna@melissa.tv     |
| Clementine Bauch   | Nathan@yesenia.net    |

Cada ítem muestra el **nombre** y el **correo** de un usuario.

## 🗂️ Estructura del Proyecto

```
app/src/main/java/newcom/example/userlistappjava/
├── ApiService.java
├── MainActivity.java
├── RetrofitClient.java
├── User.java
└── UserAdapter.java

app/src/main/res/layout/
├── activity_main.xml
└── item_user.xml

app/src/main/AndroidManifest.xml
```

## 📜 Explicación de Cada Archivo

(Explicación completa de MainActivity, User, UserAdapter, ApiService y RetrofitClient con sus funciones principales.)

## 🌐 ¿De Dónde se Consume la API?

Usamos:

```
https://jsonplaceholder.typicode.com/users
```

que devuelve un JSON con usuarios ficticios (ID, nombre y email).

## 🤔 ¿Por Qué Trae Esta Información?

- **JSONPlaceholder** es una API gratuita de prueba.
- Permite obtener datos simulados sin tener que montar un backend real.
- Ideal para desarrollo y pruebas de consumo de APIs.

## 🔥 ¿Cómo Fluyen los Datos?

```
MainActivity → RetrofitClient → ApiService → API /users → JSON → List<User> → UserAdapter → RecyclerView
```

1. **MainActivity** llama a `getUsers()`.
2. **RetrofitClient** crea una instancia de Retrofit.
3. **ApiService** define el endpoint `GET /users`.
4. Retrofit hace la petición y recibe un JSON.
5. **Gson** convierte ese JSON en `List<User>`.
6. **UserAdapter** toma la lista y la pasa al **RecyclerView**.
7. **RecyclerView** muestra la lista en pantalla.

## ✅ Resumen

**UserListAppJava**:
- Conecta a una API REST externa.
- Descarga datos en formato JSON.
- Convierte JSON a objetos Java.
- Muestra dinámicamente en un RecyclerView.

