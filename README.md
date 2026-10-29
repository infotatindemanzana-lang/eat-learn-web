# Web Eat & Learn — publicación

Web estática (HTML + CSS + JS, sin build en el servidor). Todo lo que hay en esta carpeta se publica tal cual con GitHub Pages.

> Esta carpeta se genera con `node web-v2-handoff/build.cjs` desde el proyecto. Para cambiar algo, edita el diseño o la config de `build.cjs` y vuelve a generar; no edites `index.html` a mano.

## 1. Subir a GitHub

1. Crea un repositorio nuevo en GitHub (p. ej. `eat-learn-web`). Puede ser público o privado (privado requiere plan de pago para Pages).
2. Sube el contenido de esta carpeta a la raíz del repo, rama `main`:
   ```
   git init -b main
   git add .
   git commit -m "Web Eat & Learn"
   git remote add origin https://github.com/USUARIO/eat-learn-web.git
   git push -u origin main
   ```
3. En el repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `(root)`** → Save.
4. En **Settings → Pages → Custom domain** escribe el dominio (el mismo que hay en el fichero `CNAME`) → Save.

## 2. Cambiar los DNS (en el proveedor del dominio)

Borra los registros A/AAAA/CNAME que apunten al hosting antiguo y crea estos:

| Tipo  | Nombre | Valor |
|-------|--------|-------|
| A     | @      | 185.199.108.153 |
| A     | @      | 185.199.109.153 |
| A     | @      | 185.199.110.153 |
| A     | @      | 185.199.111.153 |
| AAAA  | @      | 2606:50c0:8000::153 |
| AAAA  | @      | 2606:50c0:8001::153 |
| AAAA  | @      | 2606:50c0:8002::153 |
| AAAA  | @      | 2606:50c0:8003::153 |
| CNAME | www    | USUARIO.github.io |

**No toques los registros MX ni TXT** (son los del correo): si los borras, deja de llegar el email.

## 3. HTTPS

Cuando GitHub detecte los DNS (de minutos a unas horas), en **Settings → Pages** marca **Enforce HTTPS**. Hasta que no se emite el certificado la casilla sale gris: es normal.

## Antes de anunciarla

- Completar los datos marcados como `[PENDIENTE]` en `privacidad.html` y `aviso-legal.html` (razón social, NIF, domicilio).
- Las tipografías ABC son versiones *Trial*: sustituirlas por las licencias compradas.
