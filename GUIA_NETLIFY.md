# 🚀 Guía Paso a Paso: Desplegar en Netlify

## OPCIÓN A: Deployment Más Fácil (Drag & Drop) - 2 minutos

### Paso 1: Descargar archivos
- Descarga todos los archivos que te proporcioné
- Carpeta local: `paw-tracker-landing/`

### Paso 2: Ir a Netlify
1. Abre [netlify.com](https://netlify.com)
2. Si no tienes cuenta, haz click en "Sign up" (puedes usar Google)
3. Una vez adentro, verás un área gris que dice "Drag and drop your site"

### Paso 3: Arrastrar y soltar
1. Abre el explorador de archivos / Finder
2. Abre la carpeta con todos tus archivos
3. Selecciona TODOS los archivos (Ctrl+A o Cmd+A)
4. Arrastra y suelta en Netlify
5. ¡Listo! Tu sitio estará en línea en 10-20 segundos

**Resultado:** Tu URL será algo como `https://xxx-xxx-123.netlify.app`

---

## OPCIÓN B: Deployment Profesional (Con Git) - 10 minutos

Este método es mejor si quieres actualizar el contenido constantemente.

### Paso 1: Crear cuenta en GitHub
1. Abre [github.com](https://github.com)
2. Click en "Sign up"
3. Completa el registro (es gratis)
4. Verifica tu email

### Paso 2: Crear nuevo repositorio
1. Una vez en GitHub, haz click en el ícono "+" arriba a la derecha
2. Selecciona "New repository"
3. **Nombre del repositorio:** `paw-tracker-landing`
4. **Descripción:** GPS para mascotas - Landing Page
5. Selecciona "Public" (para que Netlify pueda acceder)
6. **NO marques** "Add a README file"
7. Click en "Create repository"

### Paso 3: Descargar Git (si no lo tienes)
1. Ve a [git-scm.com](https://git-scm.com)
2. Descarga e instala (sigue los pasos por defecto)
3. Abre Terminal (Mac/Linux) o Git Bash (Windows)

### Paso 4: Subir archivos a GitHub
En Terminal/Git Bash, ejecuta:

```bash
# Navega a tu carpeta
cd ~/Descargas/paw-tracker-landing

# Inicializa Git
git init

# Agrega todos los archivos
git add .

# Crea el primer commit (cambio)
git commit -m "Lanzamiento inicial de Paw Tracker"

# Renombra rama a main
git branch -M main

# Conecta con tu repositorio en GitHub (reemplaza TU_USUARIO)
git remote add origin https://github.com/TU_USUARIO/paw-tracker-landing.git

# Sube los archivos
git push -u origin main
```

**Nota:** Si pide tu contraseña, usa tu token de GitHub (crearás uno en el siguiente paso)

#### Crear Token de GitHub (si lo pide):
1. En GitHub, ve a Settings (arriba a la derecha) → Developer settings → Personal access tokens
2. Click en "Generate new token"
3. Dale nombre: "Netlify"
4. Dale permisos de repositorio
5. Click "Generate token"
6. **COPIA el token** (no lo verás nuevamente)
7. En Terminal, cuando pida contraseña, pega el token

### Paso 5: Conectar GitHub a Netlify
1. Abre [netlify.com](https://netlify.com)
2. Inicia sesión
3. Click en "New site from Git"
4. Selecciona "GitHub"
5. Autoriza Netlify a acceder a GitHub
6. Selecciona el repositorio `paw-tracker-landing`
7. Configura:
   - **Branch to deploy:** main
   - **Build command:** (dejar en blanco)
   - **Publish directory:** . (punto)
8. Click "Deploy site"

**¡Listo!** Tu sitio está en línea y se actualiza automáticamente cuando hagas cambios.

---

## OPCIÓN C: Deployment Sin Código (La Más Rápida)

Si no quieres tocar Git ni Terminal:

1. Crea una cuenta en Netlify
2. Ve a [netlify.com/drop](https://netlify.com/drop)
3. Arrastra y suelta la carpeta con todos tus archivos
4. ¡Listo!

---

## 📝 Cómo Actualizar Después

### Si usaste Opción A (Drag & Drop):
- Necesitarías volver a subir todo manualmente

### Si usaste Opción B (GitHub):
**Para cambiar un archivo:**

```bash
# Abre y edita el archivo en tu editor favorito

# Luego en Terminal:
git add .
git commit -m "Actualización: cambié los precios"
git push
```

Netlify se actualizará automáticamente en 1-2 minutos.

---

## 🎯 Cambios Comunes que Querrás Hacer

### Cambiar Email de Contacto
En `paw-tracker-landing.html`, busca:
```
marceardila@gmail.com
```
Reemplaza por tu email.

### Cambiar Link de Stripe
Busca:
```
https://buy.stripe.com/aFa9ASaiP343fIO6HWaEE03
```
Reemplaza por tu link de Stripe.

### Cambiar Precios
Busca en el HTML:
```html
Precio Regular: $250
Precio Actual: $102
Mensualmente: $8.50
```

### Cambiar Descripción del Producto
Todo el texto está en el mismo archivo HTML. Busca y reemplaza fácilmente.

---

## 🆘 Solución de Problemas

### "No veo mi sitio después de deploy"
- Espera 2-3 minutos
- Recarga la página (Ctrl+Shift+R o Cmd+Shift+R)
- Limpia el caché

### "El video/imagen no carga"
- Asegúrate de que los archivos están en la misma carpeta
- Los nombres deben coincidir exactamente (con mayúsculas/minúsculas)

### "No puedo subir a GitHub"
- Verifica que tengas Git instalado: `git --version`
- Usa un token en lugar de contraseña
- Revisa que la URL del repositorio sea correcta

### "Netlify no se actualiza"
- En GitHub, verifica que el archivo está en la rama "main"
- En Netlify, verifica en "Deploys" si hay errores
- Intenta hacer un deploy manual en Netlify

---

## 💡 Dominios Personalizado (Opcional)

Si quieres usar `www.paw-tracker.com`:

1. Compra el dominio en GoDaddy, Namecheap, etc.
2. En Netlify, ve a "Site settings" → "Domain management"
3. Click "Add custom domain"
4. Agrega tu dominio
5. Sigue las instrucciones de DNS que te dé Netlify
6. Espera 24-48 horas para que se propague

---

## ✅ Verificar que Todo Funciona

Después de desplegar:
1. ✓ Abre el sitio desde el navegador
2. ✓ Revisa que se vea bien en móvil (F12 → Toggle device toolbar)
3. ✓ Haz clic en "Comprar" - debe ir a Stripe
4. ✓ Completa el formulario - debe enviar email
5. ✓ Mira el video - debe reproducirse
6. ✓ Revisa que las imágenes se vean

---

## 🎉 ¡Listo!

Tu landing page de Paw Tracker está en línea y lista para convertir visitantes en clientes.

**Próximos pasos:**
1. Comparte el link en redes sociales
2. Analiza las métricas en Netlify Analytics (si pagas)
3. Recibe contactos en tu email
4. ¡Vende muchos GPS! 🐾

---

**Soporte:**
- Netlify: [docs.netlify.com](https://docs.netlify.com)
- GitHub: [docs.github.com](https://docs.github.com)
- Git: [git-scm.com](https://git-scm.com)
