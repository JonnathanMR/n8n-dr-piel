# n8n en Render

Blueprint para desplegar una instancia de [n8n](https://n8n.io/) en Render usando la imagen oficial de Docker y PostgreSQL como almacenamiento persistente de los flujos y credenciales.

## Recursos creados

El archivo `render.yaml` define:

- Un servicio web que ejecuta `n8nio/n8n`.
- Una base de datos PostgreSQL administrada por Render.
- Variables de entorno para conectar ambos recursos.
- Una clave de cifrado `N8N_ENCRYPTION_KEY` generada por Render.

## Despliegue

1. Haz fork o conecta este repositorio a Render.
2. Crea un nuevo **Blueprint** desde el repositorio.
3. Revisa el nombre del servicio y selecciona el plan apropiado.
4. Despliega y abre la URL que asigne Render.

## Configuración importante

- Actualiza `WEBHOOK_URL` con el dominio final del servicio antes de activar flujos con webhooks.
- No cambies `N8N_ENCRYPTION_KEY` después de que n8n haya guardado credenciales; perderías acceso a los datos cifrados previamente.
- Los planes gratuitos pueden tener límites de disponibilidad, recursos y almacenamiento. Revísalos antes de usar la instancia en producción.

## Seguridad

Configura autenticación y las variables de entorno adicionales de n8n que requiera tu entorno. No guardes secretos, claves de API ni credenciales dentro de `render.yaml`.

## Referencias

- [Documentación de n8n](https://docs.n8n.io/)
- [Blueprints de Render](https://render.com/docs/infrastructure-as-code)
