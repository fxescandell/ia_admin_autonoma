# AI Admin Autónomo ..

Admin Local con IA multiagente que planifica, crea, verifica y publica contenido en WordPress y redes (n8n), con plugins autodetectables, scheduler y Cloudflare Tunnel.

## ✨ Características
- Orquestador FastAPI + carpeta `plugins/` (manifest + entrypoint).
- Conectores: WordPress, n8n, (GA4/SC opcional).
- Scheduler (APScheduler).
- Ollama local + ruteo a modelos externos.
- Cloudflare Tunnel (sin puertos abiertos).

## 🚀 Arranque rápido
1. Clona el repo y copia `deploy/.env.example` a `.env`.
2. Edita credenciales.
3. `docker compose -f deploy/docker-compose.yml up -d`
4. Carga modelo en Ollama: `docker exec -it <ollama> ollama pull llama3`

## 🧩 Estructura
- `agent/core`: orquestador (plugin_manager, scheduler, context).
- `agent/server`: API (status, clients, tasks).
- `agent/plugins`: plugins autodetectables.
- `agent/tools`: conectores (wordpress, n8n, analytics).

## 🔐 Seguridad
- Cloudflare Access.
- Usuario WP mínimo (Application Password).
- JWT por cliente (`site_id`).

## 🧪 Tests
