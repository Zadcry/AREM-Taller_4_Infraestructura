# 🗒️ Registro de Trabajo en Clase - Taller X

## 📆 Fecha de la sesión
_Indique la fecha de la clase en que se trabajó este taller._

## 👥 Integrantes presentes
- Nombre 1
- Nombre 2
- Nombre 3

## 🧠 Actividades realizadas en clase
 
Durante la sesión se diseñó colaborativamente la arquitectura de un sistema de gestión y rastreo de paquetes con capacidades en tiempo real:
 
- **Discusión en equipo:** Se analizaron los requerimientos del sistema, identificando los actores principales (mensajeros con GPS, clientes y administradores) y los servicios clave necesarios para soportar el rastreo en tiempo real.
- **Decisiones de modelado:** Se decidió separar la base de datos relacional (usuarios, facturación, datos estáticos) de una base NoSQL distribuida (tracking, estados, eventos). Se optó por un sistema de colas de mensajería (Kafka/Kinesis) para desacoplar los servicios del API Gateway.
- **Herramientas usadas:** Se trabajó en **draw.io** para construir el diagrama de despliegue digital con todos los nodos e interacciones del sistema.
- **Alcance logrado:** Se completó el diagrama de despliegue en draw.io incluyendo clientes, CDN, balanceador de carga, API Gateway, microservicios, bases de datos relacionales y NoSQL con sus réplicas/nodos.
 
## 🧩 Boceto inicial del modelo
 
> Diagrama de despliegue elaborado en draw.io durante la sesión:
 
![Diagrama de despliegue - Sistema de rastreo de paquetes](WhatsApp_Image_2026-03-07_at_12_39_55_PM__2_.jpeg)
 
**Componentes modelados en el diagrama:**
 
- **Mobile Devices / Customer Laptops:** Puntos de entrada al sistema (mensajeros con GPS y clientes/admins).
- **CDN (Content Delivery Network):** Distribución de contenido estático para reducir latencia.
- **Cloud Load Balancer:** Distribuye el tráfico entrante entre los servicios disponibles.
- **API Gateway (Auth, Rate Limit, Routing):** Punto de entrada unificado con autenticación y enrutamiento.
- **Messaging Queue (Kafka / Kinesis):** Cola de mensajería asíncrona que desacopla el gateway de los microservicios.
- **Package Management Service:** Lógica de negocio para gestión de paquetes.
- **Real-time Tracking Service:** Rastreo en tiempo real mediante telemetría GPS.
- **Alerting & Dashboard:** Módulo de monitoreo y visualización del estado del sistema.
- **Regional Servers (Route Processing):** Procesamiento de rutas de distribución por región.
- **Regional Distribution Center:** Nodo físico regional conectado a los servidores de rutas.
- **Centralized Relational DB (Users, Billing, Static):** Base de datos relacional con 3 réplicas de lectura (Read Replica 1, 2 y 3).
- **Distributed NoSQL DB (Tracking, States, Events):** Base de datos distribuida con 3 nodos (NoSQL Node 1, 2 y 3).
 
## 🔁 Tareas definidas para complementar el taller
 
| Tarea asignada | Responsable | Fecha estimada |
|----------------|-------------|----------------|
| Modelado final y ajustes del diagrama en draw.io | Nombre 1 | 15/03 |
| Revisión y validación del diagrama contra requisitos | Nombre 2 | 15/03 |
| Redacción del informe técnico y justificación de decisiones | Nombre 3 | 16/03 |
| Investigación sobre tecnologías usadas (Kafka, NoSQL, CDN) | Nombre 1 | 16/03 |
| Preparación de la presentación final del taller | Todos | 17/03 |
 
---
 
_Este documento resume el trabajo colaborativo realizado durante la sesión del taller de Arquitectura de Software en el curso AREM - Universidad de La Sabana._
