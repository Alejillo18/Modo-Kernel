# Modo Kernel

Juego de preguntas sobre **virtualización y máquinas virtuales**, hecho para repasar el tema de la clase de Sistemas Operativos. Cada persona puede jugar sola desde el navegador.

Está basado en el capítulo 8.3 (y las secciones 1.7.5 y 1.7.6) de *Sistemas Operativos Modernos*, 3.ª edición, de Andrew S. Tanenbaum.

## Cómo se juega

- Cada partida sortea 10 preguntas de un banco de 48.
- Hay 25 segundos por pregunta.
- Después de responder se muestra la explicación y la sección del libro donde está el tema.
- Al final se obtiene un rango según los aciertos y una lista de las preguntas falladas para repasar.

### Puntaje

| Concepto | Puntos |
| --- | --- |
| Respuesta correcta | 100 |
| Bonus por rapidez | hasta +50 |
| Bonus por racha | +20 por cada acierto seguido, hasta +100 |

### Rangos

| Aciertos | Rango |
| --- | --- |
| 9 o 10 | Modo kernel |
| 7 u 8 | Hipervisor |
| 4 a 6 | SO invitado |
| 0 a 3 | Proceso de usuario |

### Teclado

- `1` a `4` o `A` a `D`: responder.
- `Enter`: pasar a la siguiente pregunta.

## Temas que cubre

- Hipervisores de tipo 1 y tipo 2
- Instrucciones sensibles y privilegiadas, Popek y Goldberg, Intel VT y AMD SVM
- Traducción binaria
- Paravirtualización (Xen, VMI)
- Virtualización de la memoria y de la entrada/salida
- Dispositivos virtuales, CPUs multinúcleo, JVM y exokernels

## Cómo usarlo

No necesita instalación ni dependencias. Es un único archivo, `index.html`.

**En local:** abrir `index.html` con el navegador.

## Estructura

```
.
├── index.html   # el juego completo (HTML, CSS y JavaScript)
└── README.md
```

## Personalizar las preguntas

Las preguntas están al comienzo del bloque `<script>` de `index.html`, en el arreglo `Q`. Cada una tiene este formato:

```js
{
  q: "Texto de la pregunta",
  o: ["Opción correcta", "Opción B", "Opción C", "Opción D"],
  a: 0,            // posición de la opción correcta en "o"
  e: "Explicación que se muestra después de responder.",
  r: "8.3.2"       // sección del libro
}
```

Las opciones se mezclan solas al jugar. Para una pregunta de verdadero o falso, usar `o: ["Verdadero", "Falso"]` y agregar `fixed: true` para que no se mezclen.

## Notas

- La mejor marca se guarda en el navegador de cada persona (`localStorage`) y no se comparte entre jugadores.
- Las tipografías (IBM Plex) se cargan desde Google Fonts. Sin conexión se usan las del sistema.

## Autores

Grupo N 9  

## Fuente

Tanenbaum, A. S. *Sistemas Operativos Modernos*, 3.ª ed. Secciones 1.7.5, 1.7.6 y 8.3.