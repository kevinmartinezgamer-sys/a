# JUEGO EN UN SOLO ARCHIVO HTML

## ✅ Cambios Realizados

El juego ahora está completamente contenido en **un solo archivo HTML**: `game.html`

### Antes:
```
assets/
├── index.html (menú principal)
├── levels/
│   ├── nivel1.html
│   ├── nivel2.html
│   ├── nivel3.html
│   ├── nivel4.html
│   └── nivel5.html
├── sounds.js
├── game-common.js
└── control-config.js
```

### Ahora:
```
assets/
└── game.html (TODO EL JUEGO)
```

## 🎮 Características del Archivo Único

### Todo Incluido:
- ✅ **5 niveles completos** con progresión automática
- ✅ **Sistema de sonidos** integrado (Web Audio API)
- ✅ **Sistema de progreso** con localStorage
- ✅ **Física y colisiones** completas
- ✅ **Enemigos con IA**
- ✅ **Diálogos narrativos**
- ✅ **Controles táctiles** para Android
- ✅ **Animaciones y partículas**

### Niveles Incluidos:

1. **Nivel 1 - El Jardín de los Recuerdos**
   - Introducción a los controles
   - Plataformas básicas
   - Sin enemigos

2. **Nivel 2 - El Bosque del Camino Corto**
   - Plataformas más complejas
   - Saltos más largos
   - Sin enemigos

3. **Nivel 3 - La Ciudad Gris**
   - Edificios y navegación vertical
   - **Primeros enemigos**
   - Más monedas

4. **Nivel 4 - Ciudad Bajo Lluvia**
   - Más enemigos
   - Plataformas móviles
   - Dificultad aumentada

5. **Nivel 5 - La Estación (Final)**
   - Nivel narrativo
   - Pocos enemigos
   - Final emotivo

## 🔧 Cómo Funciona

### Sistema de Niveles
```javascript
const LEVELS = {
  1: { title, subtitle, dialogs, build() {...} },
  2: { title, subtitle, dialogs, build() {...} },
  // ... etc
}
```

Cada nivel tiene:
- **title**: Título del nivel
- **subtitle**: Subtítulo narrativo
- **winMsg**: Mensaje al completar
- **dialogs**: Diálogos durante el juego
- **build()**: Función que construye el nivel (plataformas, enemigos, monedas)

### Progresión Automática
- Al completar un nivel, automáticamente carga el siguiente
- Transición suave de 2 segundos
- Guarda progreso en localStorage
- Al completar nivel 5, muestra "FIN DEL JUEGO"

### Sistema de Vidas
- 3 vidas iniciales
- Al perder todas las vidas, reinicia desde nivel 1
- Las monedas se mantienen entre niveles

## 📱 Compilación en GitHub

El archivo `MainActivity.java` ahora carga:
```java
webView.loadUrl("file:///android_asset/game.html");
```

### Workflow de GitHub Actions
El archivo `.github/workflows/build.yml` compila automáticamente:

1. Configura Java y Android SDK
2. Genera Gradle wrapper
3. Compila el APK
4. Sube el APK como artifact

### Para Compilar:

1. **Push a GitHub**:
```bash
git add .
git commit -m "Juego en un solo archivo"
git push
```

2. **GitHub Actions automáticamente**:
   - Detecta el push
   - Ejecuta el workflow
   - Compila el APK
   - Lo sube como artifact

3. **Descargar APK**:
   - Ve a la pestaña "Actions" en GitHub
   - Selecciona el workflow más reciente
   - Descarga el artifact "app-debug"
   - Instala el APK en tu Android

## 🎯 Ventajas del Archivo Único

### Para Desarrollo:
- ✅ Más fácil de mantener
- ✅ No hay dependencias entre archivos
- ✅ Cambios en un solo lugar
- ✅ Menos archivos que gestionar

### Para Distribución:
- ✅ Un solo archivo HTML
- ✅ Funciona offline completamente
- ✅ Más rápido de cargar
- ✅ Menos espacio en el APK

### Para GitHub Actions:
- ✅ Compilación más rápida
- ✅ Menos archivos que procesar
- ✅ APK más pequeño
- ✅ Menos posibilidad de errores

## 📊 Tamaño del Archivo

- **game.html**: ~45 KB (sin comprimir)
- **APK final**: ~2-3 MB (con Android WebView)

## 🔄 Flujo del Juego

```
Inicio
  ↓
Nivel 1 (Jardín)
  ↓
Nivel 2 (Bosque)
  ↓
Nivel 3 (Ciudad)
  ↓
Nivel 4 (Lluvia)
  ↓
Nivel 5 (Estación)
  ↓
FIN
```

Cada nivel:
1. Muestra pantalla de título
2. Jugador toca para comenzar
3. Juega el nivel
4. Completa el nivel
5. Muestra pantalla de victoria
6. Automáticamente carga siguiente nivel (2 segundos)

## 🎨 Personalización

Para modificar el juego, edita `game.html`:

### Cambiar física:
```javascript
const GRAV=0.54, JUMP_F=-13.5, SPD=3.5;
```

### Agregar/modificar niveles:
```javascript
const LEVELS = {
  6: {
    title: "NUEVO NIVEL",
    subtitle: "Descripción",
    build: () => {
      // Construir nivel aquí
    }
  }
}
```

### Cambiar colores:
Busca los valores hexadecimales en el CSS y JavaScript

## 🐛 Solución de Problemas

### El juego no carga en Android
- Verifica que `MainActivity.java` apunte a `game.html`
- Asegúrate de que el archivo esté en `app/src/main/assets/`

### GitHub Actions falla
- Verifica que el archivo `build.yml` esté correcto
- Revisa los logs en la pestaña Actions
- Asegúrate de que las versiones de Gradle sean compatibles

### El juego va lento
- Es normal en dispositivos antiguos
- Reduce el número de partículas
- Simplifica los gráficos

## 📝 Notas Técnicas

- **Motor**: JavaScript puro + Canvas 2D
- **Física**: Sistema de colisiones AABB
- **Sonidos**: Web Audio API (procedurales)
- **Almacenamiento**: localStorage
- **Controles**: Touch events + Keyboard
- **Resolución**: 800x420 (escalable)
- **FPS**: 60 (requestAnimationFrame)

---

**¡El juego completo en un solo archivo HTML listo para compilar en GitHub!** 🎮
