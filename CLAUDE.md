# Invitación de Boda — Paola & Wilmar

## Datos del evento
- **Novio:** Wilmar Fernando Herbas Márquez
- **Novia:** Paola Alejandra Dávila Vacaflor
- **Fecha:** Sábado 19 de diciembre de 2026
- **Ceremonia:** Iglesia Matriz de Camargo — 14:30 Hrs. — https://maps.app.goo.gl/DtRE2h5LQyYtvC919
- **Recepción:** Centro Recreacional Don Beymar — 16:00 Hrs. — https://maps.app.goo.gl/bfs1iS4cFo8Zd7qx5
- **WhatsApp confirmación:** +591 75440484
- **Mensaje WhatsApp:** `Me complace confirmar mi asistencia a la boda de Wilmar Fernando y Paola Alejandra. Nos vemos el sábado 19 de diciembre. ¡Estaré sin falta!`

## Padres
- **Padres del novio:** Wilmar Fernando Herbas Pasquier & Ivette Angélica Márquez
- **Padres de la novia:** Edgar Antonio Dávila Leytón & Miriam Vacaflor Hernández

## Itinerario
- 14:30 Misa religiosa
- 16:00 Recepción
- 19:00 Cena
- 20:00 Fiesta
- 01:00 Fin de la fiesta

---

## Colores del proyecto
- **Dorado:** `#C9A961`
- **Verde:** `#626a54`
- NO usar otros colores para texto principal. El dorado va en títulos y acentos, el verde en texto de párrafos y detalles secundarios.

## Fuentes
- `font-charm` — títulos de sección (ej. "CÓDIGO DE VESTIMENTA")
- `font-great-vibes` — nombres de los novios y textos cursivos elegantes
- `font-crimson` — textos tipo "Nos Casamos", subtítulos formales

## Dark mode
El `<html>` tiene `style="color-scheme: only light"` para evitar que navegadores en modo oscuro cambien los colores.

---

## Patrón de título estándar (igual en todos los componentes)
```html
<h2 class="font-charm text-2xl md:text-3xl text-[#C9A961] font-bold tracking-wide mb-4">
  TÍTULO EN MAYÚSCULAS
</h2>
<div class="flex items-center justify-center gap-3">
  <div class="w-16 h-[2px] bg-gradient-to-r from-transparent to-[#C9A961]"></div>
  <div class="w-2 h-2 rounded-full bg-[#C9A961]"></div>
  <div class="w-16 h-[2px] bg-gradient-to-l from-transparent to-[#C9A961]"></div>
</div>
```

## Filtro dorado para imágenes PNG
```css
.icono-dorado {
  filter: invert(69%) sepia(40%) saturate(502%) hue-rotate(3deg) brightness(92%) contrast(95%);
}
```
Se usa en: `iglesia.png`, `recepcion.png`, `restriccion.png`, íconos del itinerario.

## Animaciones (GSAP + ScrollTrigger)
Todos los componentes usan el mismo patrón:
1. `gsap.set(...)` para ocultar elementos inicialmente
2. `ScrollTrigger.create({ trigger: "...", start: "top 85%" })` para activar al hacer scroll
3. `onEnter` con `gsap.timeline()` para animar la entrada
4. `onLeaveBack` para resetear al salir por arriba

---

## Componentes y sus detalles

### NombresFlores.astro (Hero)
- "Nos Casamos": `font-crimson text-xl sm:text-2xl md:text-3xl lg:text-4xl text-[#C9A961]`
- Nombres: `font-great-vibes text-[2.6rem] sm:text-[3.3rem] md:text-[4rem] lg:text-[5rem]`
- Novio: `text-[#626a54]` | Novia: `text-[#6B6B6B]`
- `&`: `text-3xl sm:text-4xl md:text-5xl font-charm`
- Anillos: `w-28 h-auto sm:w-32 md:w-36 lg:w-40`

### Nombres.astro (Padres)
- "Con la bendición de Dios...": `font-great-vibes not-italic text-3xl sm:text-3xl md:text-4xl text-[#C9A961]`
- Títulos padres: `text-2xl sm:text-3xl`
- Nombres padres: `text-xl sm:text-xl`
- Sección padrinos: comentada (no hay padrinos)

### Contador.astro
- Fecha evento: `new Date("2026-12-19T14:30:00")`
- Tiene: SeparadoresDorado.webp arriba, línea ornamental con 3 puntos, esquinas decorativas, línea dorada sobre cada número

### Calendario.astro
- Diciembre 2026 empieza en martes (2 espacios en blanco antes del día 1)
- Día 19 (sábado) resaltado en dorado
- Esquinas decorativas `w-8 h-8`

### DireccionIglesia.astro
- Título: "CEREMONIA RELIGIOSA" — `font-charm text-2xl md:text-3xl text-[#C9A961] font-bold tracking-wide uppercase`
- Icono: `iglesia.png` con `.icono-dorado`
- Flores laterales: `FloresBorde.webp` a `top-2/3` ambos lados
- Hora: `font-charm text-2xl md:text-3xl text-[#626a54] font-bold`
- Mapa: https://maps.app.goo.gl/DtRE2h5LQyYtvC919

### Direccion.astro (Recepción)
- Título: "Recepción Social" — mismo estilo que DireccionIglesia
- Icono: `recepcion.png` con `.icono-dorado`
- Flores laterales: `FloresBorde.webp` a `top-2/3` ambos lados
- Hora: `font-charm text-2xl md:text-3xl text-[#626a54] font-bold`
- Mapa: https://maps.app.goo.gl/bfs1iS4cFo8Zd7qx5

### Itinerario.astro
- 5 eventos: Misa 14:30, Recepción 16:00, Cena 19:00, Fiesta 20:00, Fin 01:00
- Corazones: `bg-[#C9A961]` sólido (sin degradado)
- Texto eventos: `text-[#626a54] font-bold`
- 4 hojas en zigzag: izq `top-[20%]`, der `top-[40%]`, izq `top-[60%]`, der `top-[80%]`
- Iconos PNG con `.icono-dorado`: `iglesia.png`, `recepcion.png`, `cena.png`, `musica.png`, `despedida.png`

### GaleriaFotos.astro
- Fotos: `foto1.png`, `foto2.png`, `foto3.png`, `foto4.png` (minúsculas, .png)
- Separador superior: `Separadores.webp`
- Título: patrón estándar con "NUESTRA GALERÍA"
- Botón: borde dorado transparente que se rellena al hover

### CodigoVestimenta.astro
- Imagen: `CodigoVestimenta.webp`
- Texto: "Formal" — `font-charm text-3xl md:text-4xl text-[#C9A961] font-bold`
- Subtexto: "Vestido para damas, traje para caballeros" — `text-[#626a54]`
- Sin separador inferior (fue eliminado)

### Restriccion.astro
- Título: "SOLO PARA ADULTOS"
- Icono: `restriccion.png` con `.icono-dorado`
- Texto verde `#626a54`, sin card
- Mensaje: "Con todo el cariño del mundo, les comunicamos que esta celebración es exclusivamente para adultos."

### Despedida.astro
- Textos de párrafos: `text-[#626a54]` (todo verde, sin dorado en el mensaje)
- WhatsApp URL con mensaje pre-escrito codificado
- Trigger GSAP: `#card-despedida`

### FloresAbajo.astro
- "Te esperamos": `font-great-vibes text-[#626a54]`
- Elementos con `opacity-0` inicial, animados por GSAP al hacer scroll

---

## Imágenes disponibles en /public/imagenes/
- `Anillos.webp`, `Fondo.webp`
- `FloresBorde.webp`, `FloresIzquierda.webp`, `FloresDerecha.webp`
- `FloresIzquierdaAbajo.webp`, `FloresDerechaAbajo.webp`
- `FloresLaterales.webp`, `FloresDoradasIzquierda.webp`, `FloresDoradasDerecha.webp`
- `Hojas.webp`
- `Separadores.webp`, `SeparadoresDorado.webp`
- `CodigoVestimenta.webp`, `ConfirmarAsistencia.webp`, `VerUbicacion.webp`
- `BrilloDerecha.webp`, `BrilloIzquierda.webp`
- `iglesia.png`, `recepcion.png`, `restriccion.png`
- `cena.png`, `musica.png`, `despedida.png`
- `foto1.png`, `foto2.png`, `foto3.png`, `foto4.png`

---

## Preferencias del usuario
- No cambiar fuentes sin que lo pida explícitamente
- No cambiar colores sin que lo pida explícitamente
- Cuando pide aumentar/bajar tamaño: cambiar SOLO lo que indica, no otros elementos
- Preguntar antes de hacer cambios grandes de estructura
- Respuestas cortas y directas
