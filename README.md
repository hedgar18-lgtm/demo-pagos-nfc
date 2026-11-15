# AIT3D Software - Landing Page para Transferencias Bancarias & NFC

Landing page web estática, ultra rápida y optimizada para dispositivos móviles, tarjetas inteligentes NFC y enlaces de pago para **AIT3D Software**.

---

## 📁 Estructura del Proyecto

```text
ait3d-landing/
├── assets/
│   └── logo.png        # Logotipo local AIT3D
├── index.html          # Código principal (HTML5 + CSS + JS)
├── .gitignore          # Archivos ignorados por Git
└── README.md           # Documentación del proyecto
```

---

## ⚙️ Personalización de Datos

Abre `index.html` para verificar o editar los siguientes datos:
1. **WhatsApp**: La variable `WHATSAPP_PHONE` al final del archivo para recibir los comprobantes de transferencia directamente en tu chat.
2. **Cuentas bancarias**: Los números de CLABE, tarjeta y titular para BBVA, Santander y Nu.
3. **Logotipo**: Si deseas actualizar el logo, simplemente reemplaza el archivo en `assets/logo.png`.

---

## 🚀 Probar Localmente

Para abrir y probar la página en tu navegador:

```bash
cd ait3d-landing
python3 -m http.server 8080
```
Luego visita `http://localhost:8080`.

---

## 🐙 Inicializar y subir a tu Git

Para crear tu repositorio y subir el código manualmente:

```bash
cd ait3d-landing
git init
git add .
git commit -m "feat: landing page AIT3D Software"
git branch -M main
git remote add origin <URL_DE_TU_REPOSITORIO>
git push -u origin main
```
