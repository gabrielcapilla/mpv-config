# mpv-config
Una mirada minimalista de MPV, que otorga un aspecto accesible mientras obtienes una variedad de funcionalidades para mejorar la calidad de tus series y películas en tiempo real.

![preview-mpv](https://raw.githubusercontent.com/gabrielcapilla/mpv-config/main/preview-mpv.png)

## Requisitos
- Tener instalado MPV en tu ordenador.
- Para hacer uso de los distintos *shaders* necesitará un mínimo de 4GB de memoria RAM (8GB de memoria RAM recomendado).

## Instalación
### Instalación automática (Linux)
Ejecuta el archivo `instalar.sh`.

### Instalación manual (Linux)
Mueve los archivos a
```
$HOME/.config/mpv/
```

## Mejoras
- Interfaz adaptada para resoluciones 4K UHD.
- Interfaz remodelada para un aspecto más moderno y fácil de usar.
- Reescalado de vídeo en tiempo real utilizando la tecnología AMD FidelityFX™ Super Resolution.
- Aumento de nitidez en tiempo real utilizando la tecnología AMD Radeon™ Contrast Adaptative Sharpening.
- Reescalado mejorado y en tiempo real de series y películas animadas.
- Cambia entre modo cine y modo anime en un solo clic.
- Detección del idioma español en audio y subtítulos.
- Detección de audio externo automático.
- Miniaturas en tiempo real del metraje.
- Limite de audio máximo del 200%.

## Modo cine y Modo anime
En esta configuración se usan distintos *shaders* para poder utilizar tecnologías que mejoran la imagen en tiempo real de nuestras series y películas.

De manera predeterminada no se activa ningún tipo de mejora al vídeo, es necesario que el usuario elija en aplicar el *modo cine* o *modo anime*, dependiendo de que tipo de serie o película este reproduciendo.

### Modo cine
Para aplicar el **Modo cine** debe de presionar la combinación de teclas `CONTROL+2`. Al activar el modo cine podrá observar que la imagen se volverá más nítida de manera instantánea.

**Modo cine** utiliza la tecnología combinada de *AMD FidelityFX™ Super Resolution* y *AMD Radeon™ Contrast Adaptative Sharpening* para obtener la mejor calidad posible.

Se recomienda utilizar el modo cine en series y películas *no animadas*, ya que es donde verá los mejores resultados. En todo metraje inferior a la resolución de su monitor se verá aplicada ambas tecnologías, FSR y CAS. En el caso de que se reproduzca una serie o película con la misma resolución de su monitor, solo se aplicara el efecto de AMD Radeon™ Contrast Adaptative Sharpening, ya que no será necesario reescalar la imagen.

### Modo anime
Para aplicar el **Modo anime** debe de presionar la combinación de teclas `CONTROL+3`. Al activar el modo anime podrá observar que la imagen se volverá más nítida de manera instantánea.

**Modo anime** utiliza la tecnología combinada de los shaders *Anime4K* para obtener la mejor calidad posible.

La combinación de teclas `CONTROL+3` activara el *modo anime* para series o películas con una resolución de 1080p, pero si está reproduciendo una serie o película en una resolución 720p se recomienda utilizar el *modo anime 720p*, que se activa pulsando `CONTROL+4`.

### Desactivar Modo Cine y Modo Anime
Si quiere desactivar los modos cine y anime, simplemente presione `CONTROL+1` para desactivar los shaders.

## Detección de audio externo automático
Si desea añadir una pista de audio externa a la serie o película que esta reproduciendo, solo deberá de nombrar con el mismo nombre el archivo de audio y de vídeo.

**Ejemplo:**
Vídeo: `nombre_especifico.mp4`
Audio: `nombre_especifico.wav`

Gracias a la función `audio-file-auto=fuzzy`, MPV escaneara la misma carpeta de reproducción del archivo `.mp4` y añadirá el archivo `.wav` como pista de audio. Si encuentra un desfase de audio entre la pista de vídeo y la pista de audio, deberá de sincronizar manualmente las pistas utilizando los atajos `CONTROL + +` (*control+más*) o `CONTROL + -` (*control+menos*).

## Lista de complementos
- [ModernX](https://github.com/cyl0/ModernX)
- [Anime4k](https://github.com/bloc97/Anime4K)
- [Thumbfast](https://github.com/po5/thumbfast)
- [AMD FidelityFX™ Super Resolution](https://gist.github.com/agyild/82219c545228d70c5604f865ce0b0ce5)
- [AMD Radeon™ Contrast Adaptative Sharpening](https://gist.github.com/agyild/bbb4e58298b2f86aa24da3032a0d2ee6)

---

## Notas importantes
Los *scripts* `thumbfast.lua` y `modernx.lua` han sido ligeramente modificados para una mejor visualización en resoluciones 4K UHD.

#### Thumbfast
Se ha modificado el tamaño de la miniatura para una mejor visualización en resoluciones altas.

```lua
    max_height = 400,
    max_width = 400,
```

#### ModernX
Se ha modificado el tiempo de desvanecimiento.
```lua
    fadeduration = 600,
```

Se ha añadido el idioma español a la interfaz.
```lua
-- Localization
local language = {
	['spa'] = {
	    welcome = '{\\fs24\\1c&H0&\\1c&HFFFFFF&}Arrastra aquí un archivo o una URL para reproducirlo.',  -- this text appears when mpv starts
		off = 'Desactivado',
		na = 'n/a',
		none = 'none',
		video = 'Vídeo',
		audio = 'Audio',
		subtitle = 'Subtítulos',
		available = 'Disponible ',
		track = ' Pistas:',
		playlist = 'Lista de reproducción',
		nolist = 'Lista de reproducción vacía.',
		chapter = 'Capítulo',
		nochapter = 'Sin capítulos.',
	},
```

