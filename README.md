# LABO1-PREDICCION-FINAL

## Entrega final Kaggle · Labo 1 Virtual 2026 · Analista Jr

Alumno: Carlos Pena 
Competencia: labo-1-virtual-2026-analista-jr 
Submit final elegido: KA9150_s50_2000.csv

### Resumen

Usé workflow oficial PredFinal/z739_final_senior.ipynb, con modificaciones que surgen de mi experimento colaborativo (Problema #12, Grupo B), con los resultados de experimentos de otros compañeros y con lo sugerido por el profesor en la última clase. 
Hice algunas corridas, a las que llamé experimentos 9100, 9110, 9120, 9130, 9140 y 9150. En los experimentos que van del 9100 al 9140 hice pruebas cambiando el método del Data drifting (probé con rank_cero_fijo), el parámetro de desvío en la reducción de dimensionalidad con canaritos (fijándolo en 1), quitando numero_de_cliente y foto_mes y con un semillerio de 30.  
El workflow fnal que corrí y con el que obtuve la mayor ganancia se llama v05_CARLOS_z739_final_senior y generó la carpeta WF 9150 con los archivos que se iban generando al avanzar el código (PARAM, BO_log, prediccion, etc). A continuación paso a indicar cuáles son las modificaciones con las que conformé el workflow del exeprimento 9150.

### Modificaciones introducidas al v05_CARLOS_z739_final_senior respecto de z739_final_senior
- En la sección del Data drifting, mantuve el método deflacion. 
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

