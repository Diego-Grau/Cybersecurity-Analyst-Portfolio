# Alerta 8815 – Phishing (Spoofing Amazon)

## Time of Activity
25/03/2026 08:37 UTC

## Entities Involved
- Sender: urgents[@]amazon[.]biz  
- Recipient: h.harris@thetrydaily.thm  
- URL: http://bit[.]ly/3sHkX3da12340

## Investigation Findings
- El correo utiliza un acortador de URL y un subdominio malicioso que intenta suplantar a Amazon.  
- No hay evidencia de que el usuario haya hecho click.  
- La alerta corresponde a un intento de phishing detectado por la herramienta interna.  

## Verdict
**True Positive – Phishing** (Confianza: Alta)

## Impact Assessment
- Sin interacción de usuario.  
- No se registraron conexiones salientes ni compromisos.  

## Escalation Decision
- No es necesario escalar. La alerta fue contenida.  

## Recommended Actions
- Añadir a la lista negra `urgents[@]amazon[.]biz`.  
- Ajustar filtros de correo para mayor efectividad.  
- Formar a los empleados sobre no abrir enlaces desconocidos.  

## IOCs
- dominio: amazon[.]biz  
- URL: bit[.]ly/3sHkX3da12340  
- correo: urgents[@]amazon[.]biz
