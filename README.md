# Mary - El Juego 🎮

Juego de plataformas narrativo para Android sobre Mary y su padre.

## 🎯 Características

- **5 niveles completos** con historia emotiva
- **Un solo archivo HTML** - Todo el juego en `game.html`
- **Compilación automática** en GitHub Actions
- **Controles táctiles** optimizados para Android
- **Sistema de sonidos** con Web Audio API
- **Progreso guardado** con localStorage

## 📱 Compilar APK

### Automático (GitHub Actions):
1. Haz push al repositorio
2. Ve a la pestaña **Actions**
3. Espera a que termine la compilación
4. Descarga el APK del artifact

### Manual (local):
```bash
cd My-game-main
./gradlew assembleDebug
# APK en: app/build/outputs/apk/debug/app-debug.apk
```

## 🎮 Niveles

1. **El Jardín** - Introducción a los controles
2. **El Bosque** - Plataformas y saltos
3. **La Ciudad** - Primeros enemigos
4. **Bajo Lluvia** - Desafío aumentado
5. **La Estación** - Final narrativo

## 📂 Estructura Simplificada

```
My-game-main/
├── app/src/main/
│   ├── assets/
│   │   └── game.html          ← TODO EL JUEGO AQUÍ
│   └── java/
│       └── MainActivity.java
├── .github/workflows/
│   └── build.yml              ← Compilación automática
└── README.md
```

## 🛠️ Tecnologías

- Android WebView
- HTML5 Canvas 2D
- JavaScript (ES6)
- Web Audio API
- GitHub Actions

## 🎮 Controles

- **◀ ▶** - Mover izquierda/derecha
- **▲** - Saltar
- **Teclado**: Flechas, WASD, Espacio

## 📝 Licencia

Proyecto educativo - Libre uso
