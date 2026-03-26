# Investigación de Phishing – SOC Simulator

## Resumen

Este proyecto documenta la investigación de múltiples alertas de seguridad relacionadas con actividad de phishing dentro de un entorno SOC simulado proporcionado por TryHackMe.

El análisis se centra en identificar intentos de phishing, evaluar el posible impacto y determinar las acciones de respuesta apropiadas basadas en los datos de logs disponibles (correo electrónico, firewall y tráfico web).

---

## Objetivos

- Identificar intentos de phishing y distinguirlos de correos legítimos  
- Analizar indicadores como dominios de remitentes, URLs y direcciones IP  
- Evaluar si hubo interacción del usuario o compromiso del sistema  
- Determinar requisitos de escalación  
- Recomendar acciones de remediación  

---

## Contexto del Entorno

La investigación se realizó en un entorno SOC simulado con visibilidad limitada de logs, incluyendo:

- Logs de correo electrónico  
- Logs de firewall  
- Datos de tráfico web  

Nota: Algunos indicadores pueden no arrojar resultados en herramientas de inteligencia de amenazas reales debido a la naturaleza simulada del entorno.

---

## Resumen de Incidentes

| Alert ID | Tipo                         | Descripción                                    | Escalación |
| -------- | ---------------------------- | --------------------------------------------- | ---------- |
| 8814     | Falso Positivo               | Correo legítimo de onboarding                 | No         |
| 8815     | Phishing                     | Correo malicioso (suplantación de Amazon)    | No         |
| 8816     | Intento de Conexión Maliciosa| Conexión saliente bloqueada a URL de phishing | Sí         |
| 8817     | Campaña de Phishing          | Dominio typosquatting (suplantación de Microsoft) | Sí     |

---

## Hallazgos Clave

### 1. Técnicas de Phishing Identificadas

- Suplantación de dominio (amazon.biz)  
- Typosquatting (m1crosoftsupport.co)  
- Uso de acortadores de URL (bit.ly)  
- Tácticas de ingeniería social  

---

### 2. Reutilización de Infraestructura

- Repetición del mismo URL malicioso (bit.ly)  
- Indica actividad coordinada de phishing  

---

### 3. Nueva Infraestructura Maliciosa

- Detección de un nuevo dominio typosquatting  
- Sugiere posible campaña de phishing dirigida a usuarios  

---

### 4. Actividad de Red

- Una alerta mostró un intento de conexión saliente  
- El firewall bloqueó correctamente la conexión  
- No se estableció comunicación exitosa  

---

## Evaluación de Impacto

- Interacción del usuario: No observada  
- Tráfico saliente: Bloqueado o no detectado  
- Compromiso del sistema: No se identificó evidencia  

Todos los ataques fueron contenidos en etapas tempranas, sin compromiso confirmado.

---

## Lógica de Escalación

- **No Escalado:** Alertas sin interacción del usuario o sin impacto  
- **Escalado:**  
  - Evidencia de intentos de conexión  
  - Detección de nueva infraestructura maliciosa  
  - Potencial para una campaña más amplia  

---

## Acciones de Respuesta

- Bloquear dominios e IPs maliciosas  
- Eliminar correos de phishing de buzones afectados  
- Monitorear indicadores similares  
- Investigar hosts afectados si ocurre intento de conexión  
- Mejorar reglas de filtrado de correo  
- Promover formación de usuarios sobre concienciación en phishing  

---

## Indicadores de Compromiso (IOCs)

**Dominios:**  
- amazon.biz  
- m1crosoftsupport.co  
- bit.ly/3sHkX3da12340  

**Direcciones IP:**  
- 67.199.248.11  
- 102.89.222.143  

**Correos electrónicos:**  
- urgents[@]amazon[.]biz  
- no-reply[@]m1crosoftsupport[.]co  

---

## Lecciones Aprendidas

- La detección por sí sola no es suficiente; la evaluación de impacto es crítica  
- La ausencia de logs también es un hallazgo válido  
- No todas las alertas de phishing requieren escalación  
- Identificar patrones entre alertas permite detectar campañas  
- La documentación profesional es esencial en operaciones SOC  

---

## Habilidades Demostradas

- Análisis de phishing  
- Investigación de logs  
- Triage de incidentes (True Positive / False Positive)  
- Evaluación de impacto  
- Decisión de escalación  
- Identificación y correlación de IOCs  

---


---

## Herramientas Utilizadas

- SIEM SPLUNK (entorno simulado)  
- Herramientas internas de inteligencia de amenazas  

---

## Conclusión

Esta investigación demuestra cómo múltiples alertas aparentemente independientes pueden revelar una actividad de phishing más amplia cuando se analizan de manera colectiva.

Al correlacionar indicadores, evaluar el impacto y tomar decisiones de escalación informadas, es posible detectar y responder eficazmente a amenazas incluso en entornos con visibilidad limitada.
