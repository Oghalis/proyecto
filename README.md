![Bank Loan Default Prediction](https://via.placeholder.com/840x100/4a90e2/ffffff?text=BANK+LOAN+DEFAULT+PREDICTION)
![loan_default_2](https://github.com/Oghalis/proyecto/assets/148403071/a6f2f3b7-8687-4a81-8dd9-f5490485b4d0)


* Este repositorio forma parte de uno de los proyectos presentados durante el curso de Análisis de Datos impartido por Coding Dojo.

## Introducción
<a id="introducción"></a>
### Introducción
Aquí va el contenido de la introducción...
[Regresar al índice](#índice)



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
| open_credit                    | object       | 2              | [nopc, opc]                                 | Disponibilidad de crédito abierto (nopc = no, opc = sí).                    |
| business_or_commercial         | object       | 2              | [nob/c, b/c]                                | Indica si el préstamo es para negocios o comercial (nob/c = no, b/c = sí).  |
| loan_amount                    | int64        | 211            | [116500, 206500, 406500, 456500, 696500]    | Monto total del préstamo otorgado.                                          |
| rate_of_interest               | float64      | 131            | [4.56, 4.25, 4.0, 3.99, 4.5]                | Tasa de interés aplicada al préstamo (%).                                   |
| Interest_rate_spread           | float64      | 22516          | [0.2, 0.681, 0.3042, 0.1523, 0.9998]        | Diferencial de la tasa de interés.                                          |
| Upfront_charges                | float64      | 58271          | [595.0, 0.0, 370.0, 5120.0, 5609.88]        | Cargos iniciales.                                                           |
| term                           | float64      | 26             | [360.0, 300.0, 180.0, 312.0, 144.0]         | Duración del préstamo en meses.                                             |
| Neg_ammortization              | object       | 2              | [not_neg, neg_amm]                          | Amortización negativa (not_neg = no, neg_amm = sí).                         |
| interest_only                  | object       | 2              | [not_int, int_only]                         | Indica si es solo intereses (not_int = no, int_only = sí).                  |
| lump_sum_payment               | object       | 2              | [not_lpsm, lpsm]                            | Indica si es un pago único (not_lpsm = no, lpsm = sí).                      |
| property_value                 | float64      | 385            | [118000.0, 508000.0, 658000.0, 758000.0, 10080.0] | Valor de la propiedad.                                                 |
| construction_type              | object       | 2              | [sb, mh]                                    | Tipo de construcción (sb = sitio construido, mh = casa móvil).              |
| occupancy_type                 | object       | 3              | [pr, sr, ir]                                | Tipo de ocupación (pr = propietario, sr = arrendatario, ir = inversionista).|
| Secured_by                     | object       | 2              | [home, land]                                | Garantizado por (home = hogar, land = tierra).                              |
| total_units                    | object       | 4              | [1U, 2U, 3U, 4U]                            | Número total de unidades.                                                   |
| income                         | float64      | 1001           | [1740.0, 4980.0, 9480.0, 11880.0, 10440.0]  | Ingresos del prestatario.                                                   |
| credit_type                    | object       | 4              | [EXP, EQUI, CRIF, CIB]                      | Tipo de crédito.                                                            |
| Credit_Score                   | int64        | 401            | [758, 552, 834, 587, 602]                   | Puntuación crediticia del prestatario.                                      |
| co-applicant_credit_type       | object       | 2              | [CIB, EXP]                                  | Tipo de crédito del co-solicitante.                                         |
| age                            | object       | 7              | [25-34, 55-64, 35-44, 45-54, 65-74]         | Rango de edad del prestatario.                                              |
| submission_of_application      | object       | 2              | [to_inst, not_inst]                         | Presentación de la solicitud (to_inst = a la institución, not_inst = no a la institución). |
| LTV                            | float64      | 8484           | [98.72881356, 80.01968504, 69.3768997, 91.8865, 88.13] | Relación préstamo-valor.                                             |
| Region                         | object       | 4              | [south, North, central, North-East]         | Región geográfica.                                                          |
| Security_Type                  | object       | 2              | [direct, Indriect]                          | Tipo de seguridad (direct = directo, Indriect = indirecto).                 |
| Status                         | int64        | 2              | [1, 0]                                      | Estado del préstamo (1 = activo, 0 = inactivo).                             |
| dtir1                          | float64      | 57             | [45.0, 46.0, 42.0, 39.0, 40.0]              | Relación deuda-ingreso.                                                     |




## EDA
<a id="eda"></a>
### EDA
Aquí va el contenido del EDA...
[Regresar al índice](#índice)

## Modelo
<a id="modelo"></a>
### Modelo
Aquí va el contenido del modelo...
[Regresar al índice](#índice)

## Conclusiones
<a id="conclusiones"></a>
### Conclusiones
Aquí van las conclusiones...
[Regresar al índice](#índice)


