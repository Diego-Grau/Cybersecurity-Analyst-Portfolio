# Alerta 8816 – Intento de conexión bloqueado

## Time of Activity
25/03/2026 08:38 UTC

## Entities Involved
- Source IP: 10.20.2.17 (Hanna Harris)  
- Destination IP: 67.199.248.11  
- URL: hxxp://bit[.]ly/3sHkX3da12340

## Investigation Findings
- TryDetectThis marcó la URL como maliciosa.  
- El firewall bloqueó correctamente la conexión a la URL.  
- No hubo interacción del usuario.  

## Verdict
**True Positive – Phishing / Intento de conexión bloqueada** (Confianza: Alta)

## Impact Assessment
- No se registró impacto ni compromiso.  
- La defensa funcionó correctamente.  

## Escalation Decision
- Escalado a SOC L2 para seguimiento de la IP atacante.  

## Recommended Actions
- Añadir IP 67.199.248.11 a la lista negra.  
- Formar a los empleados sobre no entrar en enlaces desconocidos.  
- Monitorizar actividad similar en la red.  

## IOCs
- URL: bit[.]ly/3sHkX3da12340  
- IP atacante: 67.199.248.11
