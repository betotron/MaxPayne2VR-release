# Max Payne 2 VR

**Realidad virtual nativa para *Max Payne 2: The Fall of Max Payne* (2003).**
Estereoscopia real, cabeza con seguimiento, mandos y apuntado con la mano.

> 🇬🇧 **[English version here](README.en.md)**

> Mod created by **betotron** — [github.com/betotron](https://github.com/betotron)
> Powered by **[techbuzzo.com](https://techbuzzo.com)**

---

## Qué es esto

No es una pantalla flotante dentro del casco. El juego se dibuja **dos veces, una por ojo**, con
la cámara del motor movida por tu cabeza. Mueves la cabeza y el mundo se queda quieto; apuntas con
la mano y el arma va donde apuntas; das un paso y Max da un paso.

| | |
|---|---|
| Estereoscopia real | sí, dos vistas por fotograma |
| Cabeza con seguimiento | sí, giro y posición (6 grados de libertad) |
| Apuntado con la mano | sí |
| Menú del juego con los mandos | sí |
| Panel de vida y balas en el mundo | sí |
| Cinemáticas y novela gráfica | en pantalla plana flotante |

---

## Antes de empezar: qué necesitas

| | |
|---|---|
| **Max Payne 2** | la versión de Steam o de GOG |
| **DXVK** | los archivos `d3d8.dll` / `d3d9.dll` dentro de la carpeta del juego. Si usas la build **Payne Evolution**, ya vienen |
| **Un casco con OpenXR de 32 bits** | ver la tabla de abajo — **esto es importante** |
| **Drivers de la tarjeta al día** | el mod usa Vulkan, que viene con el driver |

### ⚠️ Qué runtime de realidad virtual funciona, y cuál no

Max Payne 2 es un programa de **32 bits** (de 2003). Un programa de 32 bits **solo puede usar un
runtime de OpenXR de 32 bits**. Eso deja fuera a uno muy conocido:

| runtime | ¿funciona? | por qué |
|---|---|---|
| **Virtual Desktop** | ✅ **Sí — es con el que está desarrollado y probado** | instala `virtualdesktop-openxr-32.json` |
| **Oculus / Meta Link y Air Link** | ⚠️ **Debería** — no probado | instala `oculus_openxr_32.json`, que es de 32 bits |
| **SteamVR** | ❌ **No** | solo instala `steamxr_win64.json`. **No tiene runtime de 32 bits**, así que un juego de 32 bits no puede usarlo. No es una limitación del mod |

**En resumen: usa Virtual Desktop.** Es lo único probado de principio a fin, con un **Meta Quest 3**.

---

## Instalación

### Paso 1 · Descarga los archivos

Descarga este repositorio (botón verde **Code** → **Download ZIP**) y descomprímelo.

### Paso 2 · Abre la carpeta del juego

En Steam: clic derecho sobre *Max Payne 2* → **Administrar** → **Explorar archivos locales**.

Es la carpeta donde está `MaxPayne2.exe`.

### Paso 3 · Copia los DOS archivos

> ### ⚠️ Lo más importante de toda la guía
> **La carpeta `mod` NO se copia.** Se copian **los dos archivos que hay dentro de ella**, y van
> sueltos **junto a `MaxPayne2.exe`**.

**Lo que descargas:**

```
MaxPayne2VR-release/
├── mod/
│   ├── winmm.dll            <- ESTE
│   └── MaxPayne2VR.ini      <- Y ESTE
├── README.md
└── LICENCIAS.txt
```

**Cómo tiene que quedar la carpeta del juego:**

```
Max Payne 2 The Fall of Max Payne/
├── MaxPayne2.exe
├── d3d8.dll                 <- de DXVK, ya estaba
├── d3d9.dll                 <- de DXVK, ya estaba
├── winmm.dll                <- ✅ AÑADIDO POR TI
├── MaxPayne2VR.ini          <- ✅ AÑADIDO POR TI
└── ...
```

❌ **Mal:** `Max Payne 2\mod\winmm.dll`
✅ **Bien:** `Max Payne 2\winmm.dll`

### Paso 4 · Ajusta el lanzador del juego — **no te lo saltes**

Al abrir el juego sale primero una ventanita, el lanzador. **Lo que elijas ahí decide la nitidez
de lo que verás dentro del casco.**

| opción | qué poner |
|---|---|
| **Adaptador gráfico** | tu tarjeta (no el adaptador integrado) |
| **Resolución de** | **la más alta de la lista**, y que acabe en **× 32** |
| **Aceleración** | **D3D Hardware T&L** |

**Por qué importa tanto:** el mod coge la imagen que dibuja el juego y la estira hasta el tamaño
que pide el casco. Un Quest 3 pide **2112 × 2304 por ojo**. Si dejas el juego en 800 × 600, esa
imagen se estira casi tres veces y se ve borrosa. **La resolución del lanzador es la calidad que
vas a ver.**

En un equipo de referencia, la lista llega hasta **2715 × 1527 × 32**. En el tuyo puede ser otra:
**coge siempre la última de la lista.**

### Paso 5 · Ponte el casco y juega

1. Arranca **Virtual Desktop** y conecta el casco.
2. Abre Max Payne 2 **como siempre**.
3. El mod se carga solo. No hay que ejecutar nada más.

---

## La primera vez

- **Ponte en posición T** (los dos brazos abiertos en cruz) durante un par de segundos en los
  primeros minutos. El mod mide tu brazo solo y se lo guarda. **No tienes que pulsar nada.**
- Si te ves más alto o más bajo que los personajes del juego, cambia `camara_altura_ojos` en el
  `.ini`. **Puedes hacerlo con el juego abierto:** guardas el archivo y se aplica solo.

---

## Los mandos — Meta Quest 3

Con los mandos Touch Plus. **Tu cabeza gira la cámara**, así que la palanca derecha queda libre.

### Mando derecho

| botón | qué hace |
|---|---|
| 🔫 **Gatillo** | **Disparar**. Con el selector de armas abierto, **elige el arma** |
| ✊ **Agarre** (lateral) | **Usar / interactuar** (puertas, objetos) |
| **A** | **Recargar** |
| **B** | **Saltar** |
| 🕹️ **Clic de la palanca** | **Analgésico** (painkiller) |
| 🕹️ **Palanca** | nada — giras con la cabeza |
| ✋ **Apuntar** | el arma va **donde apunta tu mano** |

### Mando izquierdo

| botón | qué hace |
|---|---|
| 🕹️ **Palanca** | **Caminar** (adelante, atrás y a los lados) |
| ✊ **Agarre** (lateral) | **Golpe cuerpo a cuerpo** |
| **X** | **Tiempo bala** (cámara lenta) |
| **Y** | **Selector de armas** — cada pulsación pasa a la siguiente; el gatillo derecho la elige |
| ☰ **Botón de las tres rayitas** | **Abrir y cerrar el menú del juego** (hace de `ESC`) |

### Dentro del menú del juego

| | |
|---|---|
| 🕹️ **Palanca izquierda** | arriba y abajo para moverte; izquierda y derecha para cambiar un valor |
| 🔫 **Gatillo** (cualquier mano) | elegir la opción |
| **B / Y** | volver atrás |

### Tu cuerpo

| | |
|---|---|
| **Girar la cabeza** | gira la cámara. El cuerpo de Max te sigue con retraso, para no marear |
| **Dar un paso de verdad** | Max camina en esa dirección |
| **Agacharte / asomarte** | el ojo se mueve de verdad (6 grados de libertad) |

### Teclas del teclado (para afinar, opcional)

| tecla | qué hace |
|---|---|
| **M** / **N** | subir / bajar la altura de los ojos, un centímetro por toque |
| **,** / **.** | juntar / separar los ojos, un milímetro por toque |

**Todos los botones se pueden cambiar** desde `MaxPayne2VR.ini`, y casi todos **con el juego
abierto**.

---

## Ajustes

Todo está en `MaxPayne2VR.ini`, en castellano y explicado **ajuste por ajuste**, con lo que hace,
qué valores admite y qué vas a notar al cambiarlo.

La mayoría se cambian **sin cerrar el juego**: guardas el archivo y el mod lo aplica solo. Los
que no, lo dicen.

---

## Si algo no funciona

| lo que ves | qué mirar |
|---|---|
| El juego abre pero **no entra en el casco** | ¿Virtual Desktop está conectado **antes** de abrir el juego? ¿Estás usando SteamVR? No puede funcionar (ver arriba) |
| Se ve **borroso** | la resolución del lanzador. Ponla al máximo (paso 4) |
| Se ve **plano**, sin relieve | falta DXVK: comprueba que `d3d8.dll` y `d3d9.dll` están en la carpeta del juego |
| **Nada** cambia al abrir el juego | `winmm.dll` está en la carpeta equivocada. Tiene que estar **junto a `MaxPayne2.exe`**, no dentro de `mod\` |
| El brazo se comporta raro | ponte en posición T unos segundos para que te vuelva a medir |

El mod deja un **registro** en la carpeta del juego que dice **qué se pidió y qué se aplicó de
verdad**. Si abres un issue, adjúntalo: contesta la mitad de las preguntas él solo.

---

## Desinstalar

Borra `winmm.dll`. El juego vuelve a ser el original.
No se ha modificado **ningún** archivo del juego en ningún momento.

---

## Créditos y licencias

Mod creado por **betotron** — [github.com/betotron](https://github.com/betotron)
Powered by **[techbuzzo.com](https://techbuzzo.com)**

*Max Payne 2: The Fall of Max Payne* es propiedad de **Remedy Entertainment** y **Rockstar
Games**. Este mod **no contiene ni distribuye ningún archivo del juego**: son dos archivos
propios que se ponen al lado. Hace falta tener el juego original.

`winmm.dll` incluye el cargador de **OpenXR** (The Khronos Group) bajo licencia Apache 2.0.
El texto completo está en [`LICENCIAS.txt`](LICENCIAS.txt).

---

## Version

| | |
|---|---|
| candidato | `C-235` |
| SHA-256 de `winmm.dll` | `76FD1F14D4E9AE3B78565A52AA1B020D3705998C1BCF5DC818430C11642F8F2E` |

