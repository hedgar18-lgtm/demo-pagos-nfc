# AIT3D Software - Landing Page para Transferencias Bancarias & NFC

Página web estática ultra rápida para pagos bancarios, transferencias SPEI y tarjetas NFC de **AIT3D Software**.

---

## 📁 Estructura del Proyecto

```text
ait3d-landing/
├── assets/
│   └── logo.png        # Logotipo local AIT3D
├── index.html          # Código principal optimizado (HTML5 + CSS + JS)
├── nginx.conf          # Configuración recomendada para Nginx en tu VPS
├── docker-compose.yml  # Configuración opcional para Docker en tu VPS
├── .gitignore          # Archivos ignorados para Git
└── README.md           # Esta guía
```

---

## ⚙️ Personalización previa al despliegue

Abre `index.html` y asegúrate de verificar:
1. **WhatsApp**: La variable `WHATSAPP_PHONE` al final del archivo para recibir los comprobantes directamente en tu chat.
2. **Cuentas bancarias**: Datos de BBVA, Santander y Nu (CLABE, número de tarjeta y titular).

---

## 🐙 Inicializar tu Git manualmente

Para subir este proyecto a tu propio repositorio de GitHub o GitLab:

```bash
cd ait3d-landing
git init
git add .
git commit -m "feat: landing page AIT3D Software"
git branch -M main
git remote add origin <URL_DE_TU_REPOSITORIO>
git push -u origin main
```

---

## 🖥️ Cómo subirla y hospedarla en tu VPS

### Opción 1: Clonar desde tu Git al VPS (Recomendada)
1. Conéctate a tu VPS por SSH:
   ```bash
   ssh usuario@IP_DE_TU_VPS
   ```
2. Clona tu repositorio en la carpeta web (por ejemplo `/var/www/`):
   ```bash
   cd /var/www
   git clone <URL_DE_TU_REPOSITORIO> ait3d-landing
   ```
3. Si usas Nginx:
   - Copia la configuración:
     ```bash
     sudo cp /var/www/ait3d-landing/nginx.conf /etc/nginx/sites-available/ait3d
     sudo ln -s /etc/nginx/sites-available/ait3d /etc/nginx/sites-enabled/
     sudo nginx -t
     sudo systemctl reload nginx
     ```
   - Para certificado SSL gratis (HTTPS):
     ```bash
     sudo certbot --nginx -d tudominio.com
     ```

---

### Opción 2: Subir los archivos directamente por SCP / Rsync
Desde tu Mac (terminal local dentro de esta carpeta):

```bash
# Con SCP:
scp -r ait3d-landing usuario@IP_DE_TU_VPS:/var/www/

# O con Rsync:
rsync -avz ait3d-landing/ usuario@IP_DE_TU_VPS:/var/www/ait3d-landing/
```

---

### Opción 3: Con Docker en el VPS
Si tienes Docker instalado en tu VPS:
```bash
cd /var/www/ait3d-landing
docker compose up -d
```
¡Tu landing page estará respondiendo de inmediato en el puerto 80!
