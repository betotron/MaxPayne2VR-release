# Max Payne 2 VR

Realidad virtual nativa para **Max Payne 2: The Fall of Max Payne** (2003).
Estereoscopia real, cabeza con seguimiento, mandos, apuntado con la mano.

    Mod created by betotron - github.com/betotron
    Powered by techbuzzo.com

---

## Qué necesitas antes de empezar

| | |
|---|---|
| **Max Payne 2** | la version de Steam o de GOG |
| **DXVK** | los archivos `d3d8.dll` / `d3d9.dll` en la carpeta del juego. Si usas la build **Payne Evolution**, ya los trae |
| **Un casco** | Quest, Index, Pico... cualquiera con runtime de **OpenXR** (Virtual Desktop, SteamVR u Oculus) |
| **Drivers al dia** | el mod usa Vulkan, que viene con el driver de tu tarjeta |

No hace falta instalar nada mas. Ni Visual Studio, ni SDKs, ni runtimes aparte.

---

## Instalacion — dos archivos

1. Abre la carpeta del juego.
   En Steam: clic derecho sobre el juego -> **Administrar** -> **Explorar archivos locales**.
2. Copia dentro los **dos** archivos de la carpeta `mod/`:

   ```
   winmm.dll
   MaxPayne2VR.ini
   ```

3. Ponte el casco, con tu runtime de OpenXR ya funcionando.
4. Abre el juego **como siempre**.

Eso es todo. El mod se carga solo.

### Para desinstalarlo

Borra `winmm.dll`. El juego vuelve a ser el original, sin tocar nada mas.

---

## La primera vez

- **Ponte en posicion T** (brazos en cruz) un momento durante los primeros minutos.
  El mod mide tu brazo solo y se lo guarda. No tienes que apretar nada.
- Si te ves demasiado alto o demasiado bajo, cambia `camara_altura_ojos` en el `.ini`.
  **Puedes hacerlo con el juego abierto**: se aplica solo.

---

## Ajustes

Todo esta en `MaxPayne2VR.ini`, en castellano y explicado ajuste por ajuste. La mayoria se
pueden cambiar **con el juego abierto**: guardas el archivo y el mod lo aplica sin reiniciar.

Si algo te sale mal, el mod escribe un registro al lado del juego que dice **que se pidio y
que se aplico de verdad**.

---

## Si algo falla

1. Mira el registro que deja el mod en la carpeta del juego.
2. Comprueba que DXVK esta puesto (`d3d8.dll` / `d3d9.dll` en la carpeta).
3. Comprueba que tu runtime de OpenXR funciona con otra aplicacion.

---

## Version

| | |
|---|---|
| candidato | C-235 |
| SHA-256 de `winmm.dll` | `76FD1F14D4E9AE3B78565A52AA1B020D3705998C1BCF5DC818430C11642F8F2E` |

---

## Creditos y licencias

Mod creado por **betotron** — https://github.com/betotron
Powered by **techbuzzo.com**

Max Payne 2 es propiedad de Remedy Entertainment y Rockstar Games. Este mod **no distribuye
ningun archivo del juego**: son dos archivos propios que se ponen al lado.

`winmm.dll` incluye el cargador de **OpenXR** (Khronos Group), bajo licencia Apache 2.0.
El texto de esa licencia esta en `LICENCIAS.txt`.
