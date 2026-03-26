# Alerta 8817 – Phishing (Typosquatting Microsoft)

## Time of Activity
25/03/2026 08:39 UTC

## Entities Involved
- Sender: no-reply[@]m1crosoftsupport[.]co  
- Recipient: c.allen@thetrydaily.thm  
- IP: 102.89.222.143  
- URL: hxxps://m1crosoftsupport[.]co/login  
- Location: Lagos, Nigeria

## Investigation Findings
- Dominio m1crosoftsupport.co intenta suplantar Microsoft (typosquatting).  
- No hay evidencia de interacción del usuario.  
- No se registraron conexiones salientes ni compromisos.  
- Indica potencial campaña de phishing activa.  

## Verdict
**True Positive – Phishing / Typosquatting** (Confianza: Alta)

## Impact Assessment
- No se detectó compromiso.  
- Potencial riesgo organizacional por nueva infraestructura maliciosa.  

## Escalation Decision
- Escalado a SOC L2 debido a posible campaña de phishing.  

## Recommended Actions
- Bloquear dominio m1crosoftsupport[.]co y IP 102.89.222.143  
- Eliminar correo de buzones afectados  
- Monitorizar para detectar dominios similares  
- Formar a empleados y reforzar conciencia sobre phishing  

## IOCs
- dominio: m1crosoftsupport[.]co  
- IP: 102.89.222.143  
- correo: no-reply[@]m1crosoftsupport[.]co
