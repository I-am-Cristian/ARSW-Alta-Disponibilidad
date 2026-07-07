# Guía de Laboratorio: Alta Disponibilidad con Application Load Balancer en AWS

## Información General

| Campo | Detalle |
|:---|:---|
| **Asignatura** | Arquitecturas de Software |
| **Plataforma** | AWS Academy Learner Lab |
| **Créditos disponibles** | 50 USD |

---

## 1. Propósito del Laboratorio

En los sistemas modernos no basta con desplegar una aplicación en un único servidor. Si ese servidor falla, el sistema completo queda fuera de servicio. La alta disponibilidad busca reducir ese riesgo mediante redundancia, balanceo de carga, detección de fallos y distribución de componentes en varias zonas de disponibilidad.

En este laboratorio, el estudiante implementará una arquitectura básica de alta disponibilidad en AWS utilizando:

- Amazon EC2
- Application Load Balancer
- Target Group
- Security Groups
- Health Checks
- Dos zonas de disponibilidad

---

## 2. Resultados de Aprendizaje

Al finalizar el laboratorio, el estudiante estará en capacidad de:

- Explicar qué es alta disponibilidad
- Diferenciar disponibilidad, tolerancia a fallos y escalabilidad
- Crear una arquitectura redundante con dos instancias EC2
- Configurar un Application Load Balancer
- Crear un Target Group con health checks
- Validar el balanceo de carga entre instancias
- Simular una falla y observar el comportamiento del balanceador
- Relacionar la solución con atributos de calidad como disponibilidad, resiliencia y tolerancia a fallos

---

## 3. Conceptos Base

### 3.1 ¿Qué es Alta Disponibilidad?

La alta disponibilidad es la capacidad de un sistema para mantenerse operativo incluso cuando alguno de sus componentes falla.

**Sistema con punto único de falla:**

Usuario
↓
Servidor único

Si ese servidor falla, el sistema queda inoperativo.

**Arquitectura de alta disponibilidad:**

        Usuario
          ↓
Balanceador de carga
    ↓             ↓
Servidor A    Servidor B

Si el Servidor A falla, el balanceador puede enviar tráfico al Servidor B.

### 3.2 Diferencia entre Disponibilidad y Escalabilidad

| Concepto | Pregunta clave |
|:---|:---|
| **Disponibilidad** | ¿El sistema sigue funcionando si algo falla? |
| **Escalabilidad** | ¿El sistema puede atender más carga si aumenta la demanda? |

Una arquitectura puede ser escalable, pero no altamente disponible si todos sus componentes están en una sola zona de disponibilidad. También puede ser altamente disponible, pero no escalar automáticamente si no se configura Auto Scaling.

### 3.3 Balanceador de Carga

Un balanceador de carga recibe solicitudes de los usuarios y las distribuye entre varios servidores.

### 3.4 Target Group

Un Target Group es un grupo de destinos a los cuales el balanceador enviará tráfico.

Target Group: tg-ha-web
├── EC2 instancia A
└── EC2 instancia B

---

## 4. LAB - Paso A Paso
