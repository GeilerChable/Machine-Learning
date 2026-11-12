Este proyecto analiza 19,321 registros transaccionales de una cadena de panaderías con el objetivo de comprender la dinámica de compra de los consumidores, evaluar la influencia del contexto ambiental y temporal (clima, temperatura y festividades) en la demanda, y descubrir patrones de venta cruzada (cross-selling).
A través de un enfoque iterativo de modelado, se demostró que mientras los modelos predictivos de clasificación supervisada basados en variables ambientales alcanzan un techo de precisión del 55%, el Análisis de Canasta de Compra (Market Basket Analysis) mediante el Algoritmo Apriori (Aprendizaje No Supervisado) revela patrones claros, medibles y altamente accionables, diferenciando drásticamente el consumo en días estándar frente a días festivos.

APRENDIZAJE SUPERVISADO.

Desempeño: Precisión global (Accuracy) estancada en 0.55.

Diagnóstico Técnico: Las variables con mayor importancia relativa (Gini Importance) fueron Temperature (0.22) y Hour (0.18). Sin embargo, la fragmentación de pesos confirma que el entorno ambiental explica el volumen general de tráfico en la tienda, pero carece de la señal individualizada necesaria para predecir qué categoría exacta comprará un cliente en una transacción aislada.

Comportamiento por Categoría: Categorías de abasto como Dairy & Spreads (F_1 = 0.76) son predecibles, mientras que Beverages (Recall = 0.04) presenta un consumo transversal a lo largo de todo el día.

APRENDIZAJE NO SUPERVISADO.

DÍAS NORMALES (Abasto Diario y Desayuno)

Productos Ancla: Milk y Bread lideran el soporte transaccional (5.7%), actuando como motores de atracción constante.

Trío Básico de Despensa: La regla (Butter, Milk) -> (Bread) registra una Confianza del 46.7% y un Lift de 2.83 (se compran juntos casi 3 veces más de lo esperado por azar).

Hábito del Té: La regla (Rusk -> Tea Powder) alcanza un Lift de 2.39 y una confianza del 38.4%.

DÍAS FESTIVOS.

Desplazamiento del Consumo: La canasta básica cede prioridad a productos de recepción social: hojaldres salados (Puffs), bebidas y repostería tradicional (Nankhatai)

Combo de Reunión: La regla (Tea Powder, Soft Drink) -> (Puff) dispara su Confianza al 73.3% con un Lift sobresaliente de 4.18.

LIMITACIONES DEL PROYECTO.

Colisiones de Timestamp: Al reconstruir cestas agrupando por Date, Time y Store_ID, existe la posibilidad de agrupar compras simultáneas de clientes distintos en cajas separadas, inflando ligeramente el soporte de ciertos ítems.

Ausencia de Datos Demográficos: La falta de historial individual de clientes (programas de lealtad) explica el techo predictivo del 55% en el modelo supervisado.

Validación Estadística: Las reglas de Apriori se priorizaron mediante métricas descriptivas (Soporte, Confianza, Lift) sin aplicar pruebas formales de independencia para reglas de soporte bajo.
