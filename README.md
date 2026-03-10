# Challenge-Telecom-X-an-lisis-de-evasi-n-de-clientes---Parte-2

## Informe de Factores de Evasión y Comparación de Modelos

### 1. Análisis de Factores Clave (Tenure y Cargos)
Basado en las visualizaciones de *boxplots* y *scatterplots*, así como en el análisis de importancia de variables, se identifican patrones claros en el comportamiento de los clientes:

*   **Relación con la Permanencia (Tenure):** Existe una correlación inversa significativa entre la antigüedad y la evasión. Los clientes con **pocos meses de permanencia** (especialmente en el primer año) muestran una probabilidad de 'Churn' drásticamente superior. 
*   **Impacto de los Cargos Mensuales:** Los clientes que cancelan el servicio suelen tener **cargos mensuales más altos** en comparación con los clientes leales. La combinación de una baja antigüedad y facturas elevadas actúa como un detonante crítico para la salida del cliente.
*   **Tipo de Contrato:** El análisis de coeficientes de la Regresión Logística confirmó que los contratos de **mes a mes** son el factor de riesgo más importante, mientras que los contratos de dos años son el principal factor de retención.

### 2. Comparación de Modelos Predictivos
Se evaluaron dos algoritmos para identificar a los clientes en riesgo:

*   **Regresión Logística:** Fue el modelo **más efectivo para la estrategia de negocio**, alcanzando un **Recall de 0.79**. Esto significa que es capaz de detectar al 79% de los clientes que realmente abandonarán la empresa. Al usar pesos balanceados (`class_weight='balanced'`), el modelo priorizó la captura de la clase 'Churn', lo cual es vital para campañas de retención proactivas.
*   **Random Forest:** Aunque obtuvo una mejor precisión general, su **Recall fue significativamente menor (0.47)**. Este modelo tiende a ser más conservador y dejó de identificar a más de la mitad de los clientes en riesgo (falsos negativos), lo que lo hace menos eficiente para una intervención preventiva.

### 3. Conclusiones y Perfiles de Riesgo
El sistema de análisis permite concluir que el **perfil de alto riesgo** está compuesto por clientes con **poca antigüedad (tenure bajo)**, vinculados mediante **contratos de mes a mes** y que perciben **cargos mensuales elevados** (posiblemente por servicios de Fibra Óptica sin promociones de lealtad). 

Se recomienda priorizar el uso del modelo de **Regresión Logística** para alimentar las campañas de marketing, dado que su alta sensibilidad (Recall) garantiza que la mayoría de los clientes propensos a la fuga reciban una oferta de retención a tiempo.
