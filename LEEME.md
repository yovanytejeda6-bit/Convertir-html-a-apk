# HTML a APK - Proyecto listo para compilar

## 1. Instalar dependencias (una vez, requiere Node.js LTS)
    npm install @capacitor/core @capacitor/cli @capacitor/android @capacitor/splash-screen
    npx cap add android

## 2. Generar iconos y splash
Convierte resources/icon.svg a resources/icon.png (1024x1024) y resources/splash.svg a resources/splash.png (2732x2732) con convertio.co o Canva.
    npm install @capacitor/assets --save-dev
    npx capacitor-assets generate --android

## 3. Copiar tu web y compilar
    npx cap sync android
    npx cap open android
En Android Studio: Build > Build APK(s). El APK queda en:
android/app/build/outputs/apk/debug/app-debug.apk

## Opción sin usar memoria del móvil (GitHub Actions, gratis)
1. Crea una cuenta en github.com y un repositorio nuevo (privado o público).
2. Sube todo el contenido de esta carpeta usando "Upload files" desde el navegador del móvil.
3. Para iconos y splash, convierte los SVG a PNG en convertio.co desde el navegador y sube `resources/icon.png` y `resources/splash.png`.
4. Entra a la pestaña **Actions**, elige **Build APK** y pulsa **Run workflow**.
5. Al terminar (unos minutos), abre la ejecución y descarga el artefacto **app-debug**. Dentro viene el `app-debug.apk`.
6. Instálalo en el móvil permitiendo "Instalar apps desconocidas".
