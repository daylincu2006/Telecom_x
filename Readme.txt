Este proyecto realiza un proceso de Extracción, Transformación y Carga (ETL) y un análisis exploratorio para entender los factores que influyen en la cancelación de clientes en la empresa Telecom X.
1. Fuente de Datos
URL de datos:
Churn_de_Clientes
2. Proceso ETL
a) Extracción
Se obtiene la data desde la URL especificada en formato JSON usando Python.
b) Transformación
Normalización:
Se normalizaron estructuras anidadas en las columnas customer, phone, account e internet, fusionándolas con el DataFrame principal.
Limpieza de datos:
Se detectaron 0 valores nulos y 0 duplicados en customerID.
Se convirtieron columnas de tipo object a float (ejemplo: Charges.Total, Charges.Monthly).
Se eliminaron las columnas originales tras la transformación.
Se creó la columna Carga diaria dividiendo los cargos mensuales por 30.
Transformación de variables categóricas:
Columnas binarias (Partner, Dependents, PhoneService, PaperlessBilling, MultipleLines) convertidas a valores binarios (1/0).
La columna 'Contract' y account.PaymentMethod fueron mapeadas numéricamente (Month-to-month → 1, etc.).
c) Carga
El DataFrame procesado se guarda en formato JSON:
3. Análisis Exploratorio
a) Proporción de clientes que abandonaron
Se generó un gráfico de barra mostrando que una proporción significativa de clientes se dio de baja.
b) Análisis por segmentos
Recuento por género, tipo de contrato y metodo de pago.
c) Análisis por variables numéricas
Cargos mensuales (Monthly Charges): Clientes que cancelan tienden a tener gastos más altos.
Tiempo de permanencia (Tenure): Los clientes que permanecen tienen mayor duración en la plataforma.
Se crearon boxplots comparando estas variables entre clientes que churnearon y los que no.
Requisitos
Python >=3.x
Bibliotecas: pandas, seaborn, matplotlib, json
Uso
Ejecutar el script principal para realizar el ETL y análisis exploratorio.

