
![Mortgage Loan Default Prediction](https://via.placeholder.com/840x100/4a90e2/ffffff?text=MORTGAGE+LOAN+DEFAULT+PREDICTION)

![loan_default_2](https://github.com/Oghalis/proyecto/assets/148403071/a6f2f3b7-8687-4a81-8dd9-f5490485b4d0)


* Este repositorio forma parte de uno de los proyectos presentados durante el curso de Análisis de Datos impartido por Coding Dojo.

# :clipboard: Tabla de contenidos
1. [Resumen del Proyecto](#sec_1)
2. [Objetivos del Proyecto](#sec_2)
3. [Dataset/ Diccionario de datos](#sec_3)
4. [Análisis Exploratorio de Datos (EDA)](#sec_4)
5. [Modelo](#sec_5)
6. [Conclusiones](#sec_6)


<a id='sec_1'></a>
# :bookmark_tabs: Resumen del Proyecto
El término "loan default" se refiere a cuando un prestatario no cumple con las condiciones de un préstamo, como los pagos de intereses o principal, debido a dificultades financieras, pérdida de empleo u otros problemas económicos. Los bancos, que generan ingresos significativos a través de préstamos hipotecarios, enfrentan el riesgo de incumplimiento por parte de los prestatarios. Los métodos tradicionales de evaluación de riesgo no siempre son precisos, por lo que este proyecto se enfoca en resolver dicho problema, utilizando técnicas avanzadas de Machine Learning para proporcionar una predicción más precisa y ayudar a los bancos a mitigar el riesgo de incumplimientos de préstamos hipotecarios.

<a id='sec_2'></a>
# :dart: Objetivos del Proyecto
## Objetivo Principal
Desarrollar un modelo de Machine Learning robusto que pueda predecir si un nuevo prestatario es probable que incumpla con un préstamo hipotecario o no, utilizando datos históricos sobre prestatarios y diversas características determinísticas.
## Objetivos Secundarios
1. Identificar los insights más importantes sobre la influencia de los atributos del cliente en el riesgo de incumplimiento.
2. Proporcionar a los bancos una comprensión detallada de los factores que impulsan el riesgo de incumplimiento y sugerir estrategias para contrarrestarlo.
3. Documentar el proceso de desarrollo del modelo y compartir el código en un repositorio público en GitHub para su revisión, colaboración y uso como referencia para futuras investigaciones y análisis relacionados con el proyecto.

<a id='sec_3'></a>
# :floppy_disk: Dataset / Diccionario de datos




| Columna                        | Tipo de Dato | Valores Únicos | Primeros 5 Valores Únicos                   | Descripción                                                                 |
|--------------------------------|--------------|----------------|---------------------------------------------|-----------------------------------------------------------------------------|
| ID                             | int64        | 148670         | [24890, 24891, 24892, 24893, 24894]         | Identificador único de cada préstamo.                                       |
| year                           | int64        | 1              | [2019]                                      | Año en que se registraron los datos.                                        |
| loan_limit                     | object       | 2              | [cf, ncf]                                   | Límite del préstamo (cf = conforme/con límite, ncf = no conforme/sin límite).                    |
| Gender                         | object       | 4              | [Sex Not Available, Male, Joint, Female]    | Género del prestatario.                                                     |
| approv_in_adv                  | object       | 2              | [nopre, pre]                                | Aprobación previa del préstamo (nopre = no previa, pre = previa).           |
| loan_type                      | object       | 3              | [type1, type2, type3]                       | Tipo de préstamo.                                                           |
| loan_purpose                   | object       | 4              | [p1, p4, p3, p2]                            | Propósito del préstamo.                                                     |
| Credit_Worthiness              | object       | 2              | [l1, l2]                                    | Valoración crediticia del prestatario.                                      |
| open_credit                    | object       | 2              | [nopc, opc]                                 | Disponibilidad de crédito abierto (nopc = no open credit/no, opc = open credit/sí).                    |
| business_or_commercial         | object       | 2              | [nob/c, b/c]                                | Indica si el préstamo es para negocios o comercial (nob/c = no, b/c = sí).  |
| loan_amount                    | int64        | 211            | [116500, 206500, 406500, 456500, 696500]    | Monto total del préstamo otorgado.                                          |
| rate_of_interest               | float64      | 131            | [4.56, 4.25, 4.0, 3.99, 4.5]                | Tasa de interés aplicada al préstamo (%).                                   |
| Interest_rate_spread           | float64      | 22516          | [0.2, 0.681, 0.3042, 0.1523, 0.9998]        | Diferencia entre la tasa de interés específica del préstamo y la tasa de referencia.                                          |
| Upfront_charges                | float64      | 58271          | [595.0, 0.0, 370.0, 5120.0, 5609.88]        | Cargos iniciales pagados al inicio del préstamo.                                                           |
| term                           | float64      | 26             | [360.0, 300.0, 180.0, 312.0, 144.0]         | Duración del préstamo en meses.                                             |
| Neg_ammortization              | object       | 2              | [not_neg, neg_amm]                          | Amortización negativa (not_neg = no, neg_amm = sí).                         |
| interest_only                  | object       | 2              | [not_int, int_only]                         | Indica si el préstamo es solo intereses durante un período específico (not_int = no, int_only = sí).                  |
| lump_sum_payment               | object       | 2              | [not_lpsm, lpsm]                            | Indica si el préstamo incluye un pago único grande al final del término (not_lpsm = no, lpsm = sí).                      |
| property_value                 | float64      | 385            | [118000.0, 508000.0, 658000.0, 758000.0, 10080.0] | Valor de la propiedad.                                                 |
| construction_type              | object       | 2              | [sb, mh]                                    | Tipo de construcción (sb = site built/sitio construido, mh = Manufactured home/casa móvil).              |
| occupancy_type                 | object       | 3              | [pr, sr, ir]                                | Tipo de ocupación (pr = primary residence/propietario, sr = second residence/arrendatario, ir = investment residence/inversionista).|
| Secured_by                     | object       | 2              | [home, land]                                | Garantizado por (home = hogar, land = tierra).                              |
| total_units                    | object       | 4              | [1U, 2U, 3U, 4U]                            | Número total de unidades (1U = flat, 2U = duplex, 3U = triplex, 4U= cuadruplex).                                                   |
| income                         | float64      | 1001           | [1740.0, 4980.0, 9480.0, 11880.0, 10440.0]  | Ingresos del prestatario.                                                   |
| credit_type                    | object       | 4              | [EXP, EQUI, CRIF, CIB]                      | Tipo de crédito (EXP = Experian, EQUI = Equifax, CRIF = CRIF, CIB = Credit Information Bureau).                                                            |
| Credit_Score                   | int64        | 401            | [758, 552, 834, 587, 602]                   | Puntuación crediticia del prestatario.                                      |
| co-applicant_credit_type       | object       | 2              | [CIB, EXP]                                  | Tipo de crédito del co-solicitante (CIB = Credit Information Bureau, EXP = Experian).                                         |
| age                            | object       | 7              | [25-34, 55-64, 35-44, 45-54, 65-74]         | Rango de edad del prestatario.                                              |
| submission_of_application      | object       | 2              | [to_inst, not_inst]                         | Presentación de la solicitud (to_inst = a la institución, not_inst = no a la institución/ realizado a través de brokers o intermediarios). |
| LTV                            | float64      | 8484           | [98.72881356, 80.01968504, 69.3768997, 91.8865, 88.13] | Relación préstamo-valor.                                             |
| Region                         | object       | 4              | [south, North, central, North-East]         | Región geográfica.                                                          |
| Security_Type                  | object       | 2              | [direct, Indriect]                          | Tipo de seguro (direct = directo/garantía es la misma propiedad, Indriect = indirecto/garantía es otra propiedad o bien).                 |
| Status                         | int64        | 2              | [1, 0]                                      | Estado del préstamo (1 = incumplimiento/default, 0 = sin incumplimiento/no default).                             |
| dtir1                          | float64      | 57             | [45.0, 46.0, 42.0, 39.0, 40.0]              | Porcentaje deuda-ingreso.                                                     |

<a id='sec_4'></a>
## EDA
<a id="eda"></a>

<a id='sec_5'></a>
## Modelo
<a id="modelo"></a>

<a id='sec_6'></a>
## Conclusiones
<a id="conclusiones"></a>



