# Simulador de uso eficiente del laboratorio de cómputo

Prototipo web del **Proyecto Integrador de Arquitectura del Computador — Grupo 06**
(Caso N.º 12: uso eficiente de un laboratorio de cómputo).

El objetivo no es construir un sistema de monitoreo profesional, sino **demostrar cómo una
solución computacional recibe datos, los procesa, utiliza memoria y genera resultados**, y
cómo esos datos se representan internamente en el computador.

## Cómo ejecutarlo

No requiere instalación, servidor ni conexión a Internet:

1. Descarga el repositorio o abre el archivo `index.html` con doble clic.
2. También puedes usarlo en línea: **https://nodirecatac-crypto.github.io/simulador-laboratorio-computo/**

Todo está en un único archivo (`index.html`): estructura HTML, estilos CSS y lógica JavaScript.

## Qué hace

- Recibe seis entradas: uso de CPU (%), uso de RAM (%), espacio libre en disco (GB),
  capacidad total del disco (GB), minutos de inactividad de la aplicación y minutos de
  inactividad del equipo.
- Valida los datos antes de procesar (rangos 0–100, libre ≤ total, valores no negativos).
- Evalúa cada recurso contra umbrales y calcula un **estado global** con la lógica del peor caso.
- Muestra cuatro tarjetas de estado, una lista de alertas con recomendaciones y un **registro
  de operaciones** que expone los pasos internos del procesamiento.
- Presenta la representación de los datos en **decimal, binario y hexadecimal**.

## Umbrales utilizados

| Recurso | Normal | Advertencia | Crítico |
|---|---|---|---|
| CPU (%) | < 70 | ≥ 70 y < 90 | ≥ 90 |
| RAM (%) | < 70 | ≥ 70 y < 90 | ≥ 90 |
| Disco libre (%) | > 20 | ≥ 10 y ≤ 20 | < 10 |
| Inactividad de la aplicación (min) | < 20 | ≥ 20 y < 45 | ≥ 45 |
| Inactividad del equipo (min) | < 30 | ≥ 30 y < 60 | ≥ 60 |

Estado global = el más grave de los recursos evaluados.

## Escenarios predefinidos

Los tres botones superiores cargan escenarios listos para demostrar el sistema:
`Normal`, `Advertencia` y `Crítico`.

## Pruebas

El simulador se validó con 16 casos de prueba (CP-01 a CP-16) que cubren los límites de cada
umbral, la validación de entradas, la lógica del estado global y la representación numérica.
Las capturas de los escenarios están en la carpeta `evidencias/`.

## Archivos

```
index.html                     prototipo completo (HTML + CSS + JavaScript)
evidencias/captura_1_normal.png
evidencias/captura_2_advertencia.png
evidencias/captura_3_critico.png
evidencias/captura_4_validacion.png
```

## Contexto académico

- Curso: Arquitectura del Computador
- Producto: T1 — Proyecto Integrador
- Grupo: 06

Los datos que se ingresan son simulados: la intención es explicar el flujo
entrada → procesamiento → memoria → salida, no medir el hardware real.
