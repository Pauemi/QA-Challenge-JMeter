# EJERCICIO 1
## 🧪 Proyecto de Pruebas de Performance con Apache JMeter – FakeStoreAPI

Este proyecto contiene un **plan de prueba de rendimiento** desarrollado en **Apache JMeter 5.6.3**, que ejecuta una prueba de carga sobre el endpoint público `/auth/login` de [FakeStoreAPI](https://fakestoreapi.com/).  
El objetivo es alcanzar **20 TPS (Transacciones por segundo)**, con un **tiempo de respuesta ≤ 1.5 segundos** y **Error % < 3%**, validando la autenticación correcta y la generación del token.

---

## 🧰 1. Prerrequisitos

Para poder ejecutar el proyecto correctamente, asegurese de tener lo siguiente configurado:

- 💻 **Sistema operativo:** Windows 10 o superior  
- ☕ **Java JDK:** versión 17 (debe estar configurada en la variable de entorno `JAVA_HOME`)  
- 🧩 **Apache JMeter:** versión 5.6.3  
- 📂 **Estructura de carpetas:**
Challenge JMeter
├─ ThreadGroup.jmx
├─ users.csv
├─ README.md
└─ .gitignore
## 🚀 2. Instrucciones para ejecutar los test
✅ Ejecución desde la interfaz gráfica (GUI)

Abra el archivo ThreadGroup.jmx con JMeter GUI
Configure:

CSV Data Set Config: users.csv, username,password, ignoreFirstLine=true, delimiter=,

HTTP Sampler Body:

{
  "username": "${username}",
  "password": "${password}"
}

Thread Group:
Threads: 30
Ramp-up: 60 s
Duration: 300 s
Scheduler: activado
Loop: forever
Constant Throughput Timer: 1200 samples/minute
Assertions:
Response Code 200 o 201
Body contiene "token"
Duración ≤ 1500 ms
Ejecute con el botón ▶️ y observe los resultados en Summary Report o Aggregate Report.

## 📊 3. Validaciones esperadas
Métrica	Criterio
Throughput	~20 requests/segundo
Tiempo medio	≤ 1.5 s
Error %	< 3%
Código HTTP	200 o 201
Respuesta	Contiene "token"
## ℹ️ 4. Información adicional
Archivo CSV (users.csv):
Contiene los usuarios que se usan para autenticar en el endpoint:

username,password
donero,ewedon
mor_2314,83r5^_

# EJERCICIO 2
Reporte de pruebas realizadas con JMeter
Puede encontrar el reporte en el siguiente link : 👉 [Ver informe de pruebas](https://github.com/Pauemi/QA-Challenge-JMeter/blob/main/InformeResultadoPruebas.docx)
