# LABO1-PREDICCION-FINAL

## Entrega final Kaggle · Labo 1 Virtual 2026 · Analista Jr

Alumno: Carlos Pena Competencia: labo-1-virtual-2026-analista-jr Submit final elegido: KA9110_s0_1700.csv

### Resumen

Usé workflow oficial PredFinal/z739_final_senior.ipynb, con modificaciones que surgen de mi experimento colaborativo (Problema #12, Grupo B), con los resultados de experimentos de otros compañeros y con lo sugerido por el profesor en
la última clase. 

### Modificaciones respecto de z739_final_senior
- En la sección del Data drifting, elijo el método rank_cero_fijo. 
- En la sección de reducción de dimensionalidad con canaritos, mantengo el parámetro ratio en 0,2 y pero el desvío lo defino en 1. 
- En cuanto a la sección del HP Tuning, solo dejamos para optimizar los 5 HP del baseline. Los rangos para esos 5 HP fueron (copio la celda del workflox para mostrar los rangos de cada HP): 
PARAM$hipeparametertuning$hs <- makeParamSet(
  makeNumericParam("num_iterations", lower= 2.0, upper= 10.0, trafo= function(x) round(2^x) ),
  makeNumericParam("num_leaves", lower= 2.0, upper= 11.0, trafo= function(x) round(2^x) ),
  makeNumericParam("learning_rate", lower= -7.0, upper= -0.1, trafo= function(x) 2^x ),
  makeNumericParam("feature_fraction", lower= 0.05, upper= 0.90),
  makeNumericParam("min_sum_hessian_in_leaf", lower= -10.0, upper= 10.0, trafo= function(x) 2^x)
)
- Apliqué un semillerío de 30
- El rango de envíos a Kaggle fue de 1300 a 1700, cada 100. 
