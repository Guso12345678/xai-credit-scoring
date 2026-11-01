# Datos

Los datos en bruto no se suben al repositorio. El notebook los descarga solo la primera vez.

## Dataset: Default of Credit Card Clients (Taiwán, 2005)

- Fuente: UCI Machine Learning Repository, dataset id 350
  https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients
- Licencia: CC BY 4.0 (según la página de UCI)
- Contenido: 30.000 clientes de tarjeta de crédito y 23 variables: límite de crédito, sexo, educación,
  estado civil, edad, estado de pago de seis meses (PAY_0, PAY_2 a PAY_6), importe de la factura
  (BILL_AMT1 a 6) e importe pagado (PAY_AMT1 a 6). La variable objetivo es el impago del mes siguiente.
  Periodo: abril a septiembre de 2005.
- Referencia: Yeh, I-C. y Lien, C-H. (2009). The comparisons of data mining techniques for the predictive
  accuracy of probability of default of credit card clients. Expert Systems with Applications, 36(2), 2473-2480.

## Cómo se cargan

1. Automático: el notebook usa `ucimlrepo.fetch_ucirepo(id=350)` y renombra las columnas.
2. Manual: si no hay conexión, descarga el CSV desde la página de UCI y guárdalo como
   `data/taiwan_default.csv`. Si ese fichero existe, el notebook lo usa en vez de descargar.

## Limpieza que se aplica

- Se eliminan 35 filas duplicadas (quedan 29.965).
- Los códigos de EDUCATION y MARRIAGE que no vienen en la descripción oficial se agrupan en "otros".
- No hay valores nulos.
- La descripción de UCI solo define PAY = -1 (pago a tiempo) y de 1 a 9 (meses de retraso), pero en los
  datos aparecen también los valores -2 y 0 sin documentar. Se mantienen tal cual y se menciona como
  limitación en el informe.
- El sexo no se usa como variable de entrada del modelo y se guarda aparte para la auditoría de equidad.
