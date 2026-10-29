# Liquidador de Gordos

Indicador para TradingView escrito en Pine Script v5. Combina deteccion de **Fair Value Gaps (FVG)**, bloques de orden, mitigacion dinamica, filtro de volumen y medias moviles exponenciales.

> Este proyecto es una herramienta visual de analisis tecnico. No constituye asesoramiento financiero ni garantiza resultados.

## Funcionalidades

- Detecta desequilibrios alcistas y bajistas (Fair Value Gaps) confirmados.
- Dibuja zonas de bloques de orden basadas en la vela de origen.
- Aplica un filtro automatico segun la temporalidad entre 1H y 1D, o permite definirlo manualmente.
- Puede exigir volumen superior a la media de 20 periodos para validar el impulso.
- Mitiga progresivamente las zonas a medida que el precio consume liquidez.
- Elimina o conserva visualmente los bloques invalidados.
- Muestra EMA 7, EMA 25 y EMA 200 con colores configurables.
- Permite limitar la cantidad de bloques visibles y activar senales de rechazo.

## Instalacion en TradingView

1. Abre un grafico en [TradingView](https://www.tradingview.com/).
2. Entra en **Pine Editor** y crea un script nuevo.
3. Copia el contenido de [Liquidador de Gordos.txt](Liquidador%20de%20Gordos.txt) en el editor.
4. Pulsa **Guardar** y despues **Anadir al grafico**.

El archivo mantiene la extension `.txt` para conservar el codigo original. TradingView puede ejecutar el contenido como Pine Script v5 desde su editor.

## Parametros principales

### Precision y filtros

- **Filtro automatico por temporalidad**: adapta el umbral del FVG a la temporalidad del grafico.
- **Filtro manual %**: umbral usado cuando el filtro automatico esta desactivado.
- **Exigir volumen institucional en impulso**: valida el impulso comparando el volumen con su media de 20 periodos.
- **Multiplicador de volumen**: define cuanto debe superar el volumen a su media.
- **Grosor de la zona**: usa la mecha real de la vela de origen o una zona acotada por ATR.
- **Mitigacion dinamica**: reduce una zona cuando el precio entra parcialmente en ella.

### Visualizacion FVG

- **Fair Value Gaps**: muestra u oculta las cajas del desequilibrio.
- **Cantidad de bloques**: limita los bloques alcistas y bajistas conservados en pantalla.
- **Mostrar bloques rotos**: conserva las zonas invalidadas en lugar de eliminarlas.
- **Senales de rechazo**: muestra marcas cuando el precio rechaza una zona.

### Medias moviles

Cada EMA puede activarse o desactivarse de forma independiente y tiene un color configurable:

- EMA 7
- EMA 25
- EMA 200

## Consideraciones

- Las zonas se calculan con velas confirmadas y pueden cambiar segun la temporalidad y el activo.
- El volumen disponible depende del mercado y del simbolo seleccionado.
- La configuracion adecuada debe validarse con datos historicos y en condiciones de mercado reales antes de tomar decisiones.
- El indicador no ejecuta operaciones ni genera entradas o salidas automaticas.

## Licencia

Este repositorio no incluye una licencia explicita por el momento. Todos los derechos sobre el codigo permanecen con su autor hasta que se publique una licencia.
