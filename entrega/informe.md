# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 4: Mapa de Infraestructura y Diagnóstico Técnico_

## 👥 Integrantes del equipo
- Julián Mauricio Zafra (julianzamo@unisabana.edu.co)
- Santiago Araque (santiagoaral@unisabana.edu.co)
- Juan José Forero (juanfope@unisabana.edu.co)

## 🧠 Descripción general del trabajo
En el presente trabajo se llevó a cabo la elaboración del mapa de infraestructura del sistema real del cliente, enfocado en las operaciones de THEGEEKHUB. El objetivo principal de este taller fue realizar un diagnóstico técnico exhaustivo para identificar debilidades o cuellos de botella reales o potenciales en su flujo de trabajo actual. La actividad se desarrolló analizando la transición de un negocio manejado a través de redes sociales y hojas de Excel hacia un modelo más limpio y estructurado que garantice la consistencia en los datos. Finalmente, este modelado se complementó con la redacción de un informe técnico y una investigación sobre buenas prácticas de arquitectura de infraestructura (cloud, on-premise, híbrida) para proponer soluciones viables a largo plazo.

## 🔧 Proceso de desarrollo
Nuestro proceso de desarrollo se realizó de manera progresiva, tomando como base el modelo entidad-relación construido en etapas anteriores y las necesidades de expansión del negocio. Las decisiones arquitectónicas se ajustaron de la siguiente manera:
- Integración de canales y validación: Lo primero que modelamos fueron los puntos de entrada del sistema. Se definió un API Gateway / Controlador encargado de centralizar y validar las ventas provenientes de los canales externos (Instagram, Facebook, Mercado Libre) y del Dashboard de socios donde actualmente manejan el registro en Excel.
- Gestión de tráfico y asincronismo: Para evitar cuellos de botella durante picos de transacciones, tomamos la decisión de implementar una "Cola de Eventos de Venta". Esta herramienta actúa como un amortiguador que recibe las peticiones validadas y las distribuye de forma asíncrona hacia los servicios internos.
- Estructuración de microservicios: Separamos la lógica del negocio en dos componentes clave. Por un lado, el "Servicio de Ventas y Referencias" para otorgarle de forma estándar un SKU a cada producto y gestionar el inventario. Por otro lado, un "Servicio de Tracking Financiero" dedicado exclusivamente a la integración con pasarelas de pago (MercadoPago, Nequi) y el manejo de retiros.
- Estrategia de persistencia de datos: Para el almacenamiento, decidimos dividir la responsabilidad. Implementamos una Base de Datos Relacional Central orientada a garantizar la consistencia de las entidades fundamentales (Ventas, Compradores, Referencias), complementada con réplicas de lectura para Inventario y Clientes.
- Auditoría y trazabilidad: Como ajuste final para asegurar un registro adecuado de la información financiera, se incluyó una base de datos NoSQL. Esta herramienta se utiliza para guardar el historial, los logs de transacciones y facilitar auditorías, garantizando que el sistema sea más profesional y seguro de cara al futuro.

## 🧩 Análisis del modelo propuesto
Incluya un análisis sobre:
- Cómo se estructura el modelo entregado
- Cómo representa las necesidades del cliente
- Qué supuestos se tomaron

## 📈 Diagrama final entregado
> (Inserte aquí una imagen o enlace al modelo-final.drawio / .asta / PDF)

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Ej: Paciente        | Actor | Usuario que agenda una cita médica | Cliente |

## 🔍 Investigación complementaria
### Tema investigado:
(Ej: Buenas prácticas BPMN, comparación TOGAF vs C4, principios de seguridad STRIDE, etc.)

### Resumen:
Describa en 2–3 párrafos lo investigado, citando fuentes cuando sea necesario. Incluya cómo se relaciona con el taller.

## 📚 Referencias
- [1] Apellido, Nombre. *Título*. Año. URL o DOI.
- [2] Fuente oficial BPMN: https://www.omg.org/spec/BPMN/

---

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
