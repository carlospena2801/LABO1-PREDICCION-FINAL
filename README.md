# LABO1-PREDICCION-FINAL

## Entrega final Kaggle · Labo 1 Virtual 2026 · Analista Jr

Alumno: Carlos Pena 
Competencia: labo-1-virtual-2026-analista-jr 
Submit final elegido: KA9150_s50_2000.csv

### Resumen

Usé workflow oficial PredFinal/z739_final_senior.ipynb, con modificaciones que surgen de mi experimento colaborativo (Problema #12, Grupo B), con los resultados de experimentos de otros compañeros y con lo sugerido por el profesor en la última clase. 
El workflow que corrí se llama v05_CARLOS_z739_final_senior y generó la carpeta WF 9150 con los archivos que se iban generando al correr el código (PARAM, BO_log, prediccion, etc). 

### Modificaciones respecto de z739_final_senior
- En la sección del Data drifting, elegí el método deflacion. 
- En la sección de reducción de dimensionalidad con canaritos, mantuve el parámetro ratio en 0,2 y el desvío en 2.
- Las iteraciones de la OB las fijé en 500. 
- En cuanto a la sección del HP Tuning, solo dejé para optimizar los 5 HP del baseline. Los rangos para esos 5 HP fueron (copio la celda del workflox para mostrar los rangos de cada HP): 

PARAM$hipeparametertuning$hs <- makeParamSet(
makeNumericParam("num_iterations", lower= 2.0, upper= 10.0, trafo= function(x) round(2^x) ),
makeNumericParam("num_leaves", lower= 2.0, upper= 11.0, trafo= function(x) round(2^x) ),
makeNumericParam("learning_rate", lower= -7.0, upper= -0.1, trafo= function(x) 2^x ),
makeNumericParam("feature_fraction", lower= 0.05, upper= 0.90),
makeNumericParam("min_sum_hessian_in_leaf", lower= -10.0, upper= 10.0, trafo= function(x) 2^x)
)
- Apliqué un semillerío de 50

