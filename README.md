# MARY — El Camino a Casa

Juego pixel-art HTML5 narrativo de 5 niveles. Mary corre hacia la estación para recibir la última carta de su padre antes de su fusilamiento.

## 📦 Estructura

```
MaryGame_Android/
├── .github/workflows/
│   └── build.yml                    ← GitHub Actions: compila APK automáticamente
├── app/
│   ├── build.gradle                 ← Configuración de la app
│   ├── proguard-rules.pro
│   └── src/main/
│       ├── AndroidManifest.xml      ← Manifest con permisos
│       ├── java/com/marygame/app/
│       │   └── MainActivity.java    ← WebView que carga el juego
│       ├── assets/                  ← Aquí va el juego (HTML+audio)
│       │   ├── index.html           ← El juego completo
│       │   └── audio/
│       │       └── cry.mp3          ← Audio del llanto de Mary
│       └── res/                     ← Iconos, themes, strings
├── gradle/wrapper/
│   └── gradle-wrapper.properties    ← Versión de Gradle
├── audio/cry.mp3                    ← Copia del audio (para la versión web)
├── MaryGame.html                    ← Versión web del juego
├── build.gradle                     ← Build raíz
├── settings.gradle
├── gradle.properties
└── README.md                        ← Este archivo
```

---

## 🚀 Cómo compilar el APK con GitHub Actions

### Paso 1: Sube este proyecto a GitHub

```bash
cd MaryGame_Android
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

### Paso 2: GitHub Actions compila automáticamente

Al subir el código, **GitHub Actions ejecuta automáticamente** `build.yml` y compila el APK. Puedes verlo en la pestaña **Actions** de tu repositorio.

### Paso 3: Descarga el APK

1. Ve a la pestaña **Actions** en tu repo
2. Click en el último workflow exitoso
3. Baja hasta la sección **Artifacts**
4. Descarga `MaryGame-APK.zip`
5. Descomprime y obtienes `MaryGame-debug.apk`
6. Cópialo a tu Android e instálalo (debes activar "Orígenes desconocidos")

---

## 🎮 Cómo probar el juego sin Android (en navegador)

Abre `MaryGame.html` en cualquier navegador. Funciona en PC y móvil.

⚠️ **IMPORTANTE**: La carpeta `audio/` debe estar **junto** a `MaryGame.html` para que se escuche el llanto del final.

---

## 🎬 Niveles

| # | Nivel | Mecánica |
|---|-------|----------|
| 1 | **El Barrio** | Saltos sobre cajas y huecos |
| 2 | **El Bosque** | Lianas con física péndulo |
| 3 | **Vieja Fábrica** | Cintas transportadoras, robots |
| 4 | **Ciudad bajo Lluvia** | Suelo resbaladizo, vehículos |
| 5 | **La Estación** | Final narrativo con carta del padre |

---

## ⌨ Controles

**PC:**
- `←` `→` o `A` `D` = Mover
- `Espacio` o `W` o `↑` = Saltar
- `S` o `↓` = Agacharse
- `ESC` = Pausar

**Móvil:** botones táctiles configurables en ⚙ CONTROLES (presets PEQUEÑO / MEDIANO / GRANDE / XL).

---

## 🔊 Audio

- **Música ambiental** generada por Web Audio API (no requiere archivos)
- **Efectos** (saltar, monedas, morir, ganar) generados por código
- **Llanto final de Mary**: archivo `audio/cry.mp3` (cargado externamente para máxima compatibilidad con WebView Android)
- **Disparo del fusilamiento**: generado por código (ruido blanco + sawtooth)

---

## 🛠 Compilar localmente (opcional)

Si quieres compilar en tu PC sin GitHub:

```bash
# Requisitos: JDK 17 y Gradle 8.7
gradle wrapper --gradle-version 8.7
chmod +x gradlew
./gradlew assembleDebug
```

El APK se genera en `app/build/outputs/apk/debug/app-debug.apk`.

---

## 📜 Tecnologías

- **HTML5 Canvas** para renderizado del juego
- **Web Audio API** para música y efectos generados
- **Vanilla JavaScript** (sin frameworks)
- **Android WebView** como contenedor para la app
- **Gradle 8.7** + **Android SDK 34** para la compilación
- **Java 17** para MainActivity
- **GitHub Actions** para CI/CD

---

## 🎨 Características

- 5 niveles narrativos con historia completa
- Pixel art generado proceduralmente con Canvas
- Sistema de partículas (lluvia, hojas, luciérnagas, etc.)
- Diálogos con texto animado
- Menú de configuración persistente (localStorage)
- Vibración táctil opcional
- Pantalla completa
- Vista previa en vivo de los controles

---

## Versión

**3.2** — Estructura completa para Android + Web, audio externo, GitHub Actions.
