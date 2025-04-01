# **Análisis de Pruebas A/B en Cookie Cats**

## **Descripción del Proyecto**
Este proyecto analiza los resultados de un experimento A/B realizado en el videojuego móvil **Cookie Cats**. El objetivo del experimento era evaluar el impacto de mover el primer bloqueo (gate) del juego desde el nivel 30 al nivel 40. Los jugadores fueron asignados aleatoriamente a uno de los dos grupos:
- **Gate 30**: Grupo control donde el bloqueo se encuentra después del nivel 30.
- **Gate 40**: Grupo experimental donde el bloqueo se mueve al nivel 40.

El análisis busca determinar si este cambio afecta las métricas clave del juego, como el número de rondas jugadas y la retención de los jugadores a corto y largo plazo.

---

## **Contexto**
El dataset incluye datos de **90,189 jugadores** que instalaron el juego mientras se realizaba la prueba A/B. Cada jugador fue asignado aleatoriamente a uno de los dos grupos mencionados. Los datos disponibles incluyen las siguientes variables:

- `userid`: Identificador único para cada jugador.
- `version`: Grupo al que pertenece el jugador: `gate_30` (control) o `gate_40` (experimental).
- `sum_gamerounds`: Número total de rondas jugadas por el jugador durante los primeros 14 días después de instalar el juego.
- `retention_1`: Indicador de si el jugador regresó al juego un día después de instalarlo (`True` o `False`).
- `retention_7`: Indicador de si el jugador regresó al juego siete días después de instalarlo (`True` o `False`).

---

## **Objetivo**
El objetivo principal es responder a la pregunta:  
**¿Mover el bloqueo del nivel 30 al nivel 40 mejora la experiencia y retención de los jugadores?**

Para ello, se definen las siguientes hipótesis:
- **Hipótesis nula ($H_0$):** No hay diferencias significativas entre las métricas clave (rondas jugadas y retención) entre los grupos Gate 30 y Gate 40.
- **Hipótesis alternativa ($H_1$):** Existen diferencias significativas entre las métricas clave entre ambos grupos.

---

## **Metodología**
1. **Exploración inicial:**
   - Limpieza y análisis exploratorio para entender la distribución de los datos.
   - Cálculo de estadísticas descriptivas para cada grupo.

2. **Pruebas estadísticas:**
   - Prueba t para comparar el número promedio de rondas jugadas (`sum_gamerounds`) entre los grupos.
   - Pruebas chi-cuadrado para comparar las tasas de retención a 1 día (`retention_1`) y 7 días (`retention_7`) entre los grupos.

3. **Visualización:**
   - Gráficos como histogramas, boxplots y gráficos de barras para visualizar las diferencias entre ambos grupos.

---

## **Resultados**
### **Análisis descriptivo**
- Los jugadores del grupo Gate 40 jugaron más rondas en promedio que los jugadores del grupo Gate 30.
- Las tasas promedio de retención a 1 día y a 7 días fueron ligeramente mayores en el grupo Gate 40.

### **Pruebas estadísticas**
1. **Prueba t para rondas jugadas:**
   - Se encontró una diferencia significativa en el número promedio de rondas jugadas entre los grupos ($p < 0.05$), lo que sugiere que mover el gate al nivel 40 aumenta la interacción.

2. **Prueba chi-cuadrado para retención a 1 día:**
   - No se encontraron diferencias significativas en la retención a corto plazo ($p \geq 0.05$).

3. **Prueba chi-cuadrado para retención a 7 días:**
   - Se encontraron diferencias significativas en la retención a largo plazo ($p < 0.05$), indicando que mover el gate al nivel 40 mejora la retención sostenida.

---

## **Conclusiones**
Los resultados sugieren que mover el bloqueo al nivel 40 tiene un impacto positivo en la experiencia general del jugador:
- Los jugadores juegan más rondas cuando el bloqueo está en el nivel 40.
- La retención a largo plazo mejora significativamente con este cambio.
- Sin embargo, no se observan cambios significativos en la retención a corto plazo (1 día).

### **Recomendación**
Se recomienda implementar el bloqueo en el nivel 40 para maximizar tanto la interacción como la retención a largo plazo.

---

## **Requisitos**
Para reproducir este análisis, necesitarás:
- Python (versión >=3.8).
- Bibliotecas: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`.

---

## **Autores**
Luis Jiménez - [@luisjimse](https://github.com/luisjimse)