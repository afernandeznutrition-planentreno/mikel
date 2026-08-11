# Plan Mikel · Registro diario

App web (PWA) para que el cliente registre cada dia su alimentacion, sus pasos y su entrenamiento,
y para que el entrenador reciba un resumen semanal.

## Que hace

- **Nutricion.** El cliente elige entre las opciones ya pautadas en su plan. La app suma kcal y macros
  y los compara con el objetivo del dia (entreno o descanso).
- **Reglas automaticas.** Al marcar el salmorejo se retira el AOVE del plato y el hidrato pasa a contar
  la mitad, con aviso en pantalla.
- **Vegetales.** Verdura, frutos rojos, sandia y melon estan marcados como calorias despreciables y no
  computan en el total.
- **Entrenamiento.** Los 4 dias del plan con peso, repeticiones y RIR por serie, autorrelleno de la
  sesion anterior y cronometro de descanso.
- **Pasos** con objetivo diario y graficas de 14 dias.
- **Resumen semanal** en texto listo para pegar en WhatsApp.

## Donde se guardan los datos

En el navegador del propio cliente (localStorage). No hay servidor ni cuenta: nada sale del movil.
La pestana Plan incluye descarga y restauracion de copias de seguridad en .json.

## Como se adapta a otro cliente

Todo lo especifico del cliente vive en el objeto DEFAULT_PLAN, al principio del script de index.html:
objetivos, catalogo de alimentos con sus valores, estructura de comidas, categorias y rutina de
entrenamiento. Para un cliente nuevo basta con duplicar el repositorio y editar ese bloque.

Los objetivos y los valores de los alimentos son fijos: el cliente los consulta pero no puede
modificarlos.

## Publicacion

Alojado con GitHub Pages desde la rama main. Al actualizar index.html, sube tambien el numero de
version de CACHE en sw.js para que el service worker sirva la version nueva.
