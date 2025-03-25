# Modelos ARIMA(p,d,q)

Analisis de una serie de tiempo con datos históricos para ajustarla de forma óptima a un modelo Box-Jenkins ARIMA(p,d,q)

Cargamos librerías y datos a utilizar
<br>![image](https://github.com/user-attachments/assets/e76f63a4-8dcc-4b49-90f6-71d672f53805)

Graficamos datos para tener un vistazo al comportamiento de los datos
<br>![image](https://github.com/user-attachments/assets/b7a9cb89-a32d-4a05-9a80-9deb94f4c7b1)

Realizamos la prueba Dickey-Fuller para ver cómo se comportan los datos inicialmente y saber si necesitamos realizar algo como aplicar diferencias
<br>![image](https://github.com/user-attachments/assets/c435de67-2e82-43de-bfa7-0c17191d0148)

Con un valor p de 0.4220 no podemos rechazar la hipótesis nula, no podemos decir que es no estacionaria

Debido al resultado, aplicamos diferencias en los datos
<br>![image](https://github.com/user-attachments/assets/1a8aa46b-087c-43fa-9ad7-f7f04c5c7096)

Volvemos a aplicar la prueba Dickey-Fuller y observamos el comportamiento
<br>![image](https://github.com/user-attachments/assets/3e1ac902-518f-46f6-928f-8adfe69fd3e1)

Conclusión: Aplicando las diferencias, podemos decir que la serie transformada de diferencias SI ES ESTACIONARIA

Solo se necesito realizar una diferencia por lo que en ARIMA, el valor a utilizar en d sería de 1

Utilizamos la funcion de autocorrelación y autocorrelación parcial para conocer el Valor AR(p)
<br>![image](https://github.com/user-attachments/assets/7babd4bf-060e-475c-a169-672d09b72682)

Obtenemos los parámetros óptimos mediante el índice de información de Akaike (a partir del resultado anterior), comparando al menos 6 combinaciones diferentes de parámetros p, d y q en el modelo general ARIMA(p, d, q).
<br>![image](https://github.com/user-attachments/assets/d40d91ae-4c52-4dc7-ba0f-15a0ce2348a2) ![image](https://github.com/user-attachments/assets/3725ef1e-68dd-4cd0-92e8-826c1c9edea2)

Al utilizar d = 1 podemos ver que no influencia en el resultado de ARIMA pero debido a la diferencia aplicada anteriormente, sabemos que 1 sería el valor óptimo a utilizar por lo que el modelo a utilizar debe ser ARIMA(1,1,1)
<br>![image](https://github.com/user-attachments/assets/bcbafb41-49e4-4112-a2d0-7c016091303c)

Obtenemos las predicciones y los intervalos de confianza para la base de prueba
<br>![image](https://github.com/user-attachments/assets/ff8f0c4e-7ab1-41b1-975d-2c2186bc71b8) ![image](https://github.com/user-attachments/assets/2151e4d1-de3a-46fb-9081-bba5d6e007a6)

Realizamos la graficación de base de entrenamiento, prueba, predicciones e intervalos
<br>![image](https://github.com/user-attachments/assets/1ea4cbb0-e4d1-4ec7-ada9-b6013781d4ca)

Evaluamos el modelo
<br>![image](https://github.com/user-attachments/assets/cbca27ba-c678-47c1-a634-e7ac6dcca0fd)

Conclusión: Los pronósticos son confiables debido a que el error es solo de 1.48% y los valores pueden estar alejados por solo 3.4
