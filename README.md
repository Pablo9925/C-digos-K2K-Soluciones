# Códigos-K2K-Soluciones
Este repositorio está dedicado al registro y gestión de códigos y automatizaciones desarrolladas para optimizar los procesos internos de K2K Soluciones, facilitando la colaboración y el seguimiento de las mejoras implementadas en la empresa.

## Librerías necesarias

**pip install PyPDF2**
**pip install selenium**
**pip install pyautogui**
**pip install openpyxl**
**pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib**

## CUFE
Este código, denominado CUFE, se encarga de obtener el estado de las facturas electrónicas. La funcionalidad principal es añadir una columna adicional que contiene valores booleanos, siendo verdaderos aquellos que indican el estado de "Aceptación expresa de la Factura Electrónica de Venta".

### Detalles del Código

- **Formato de Archivos:** Se estandarizó para leer archivos con el formato "CUFE NOKIA MES AÑO". El código extrae automáticamente el mes y el año del nombre del archivo. 

- **Nombre de la Hoja:** Se ha estandarizado el nombre de la hoja en el cual se encuentran los CUFE como "CORTE DIAN".

- **Ubicación del archivo:** El código y el archivo CUFE NOKIA se deben encontrar en la misma carpeta, para el funcionamiento del código.

## PO_Data_Extraction

Este código tiene como objetivo leer archivos PDF de Órdenes de Compra (PO) y extraer información relevante de dichos archivos. La información extraída se registra en una hoja de cálculo de Google Sheets. Aquí están los detalles clave del funcionamiento del código:

### Funcionalidades Principales

- **Lectura de Archivos PDF:** El código puede leer archivos PDF de Órdenes de Compra (PO) ubicados en una carpeta llamada "PO". Esta carpeta debe estar en la misma ubicación que el código.

- **Registro en Google Sheets:** La información extraída se registra en una hoja de cálculo de Google Sheets. Para la vinculación con Google Sheets, se requiere un archivo llamado "key.json", que debe estar presente en la misma carpeta que el código. Url donde se realiza el registro: https://docs.google.com/spreadsheets/d/11IqC9lu7w8ggmdP4kjascyZb676TIbRWDYGan2AQPko/edit#gid=0

- **Limitación de Registros:** Debido a políticas de la API de Google, solo se pueden registrar hasta 60 PO simultáneamente. El código permite distinguir las PO que ya están registradas, por lo que esta limitación se aplica solo a las nuevas PO.

## Receipt - Validación de % Released en Órdenes de Compra (SPO)

Este código tiene como objetivo validar el porcentaje de liberación (% Released) de una Órden de Compra (SPO), teniendo en cuenta el número del SPO y el SMP. Aquí se detallan las funcionalidades principales:

### Proceso de Validación

1. **Lectura de Archivos Históricos:** El código lee el archivo histórico "receipt_nokia" para obtener información sobre las liberaciones previas de las Órdenes de Compra.

2. **Comparación con PowerBI:** Utilizando el archivo local de PowerBI, compara el porcentaje pendiente de facturación (% Pending Invoiced) con el porcentaje liberado (% Released). Ajusta este valor en el archivo local, considerando las facturaciones anteriores.

3. **Organización de Carpetas:** Para el funcionamiento correcto del código, se espera que exista una carpeta con el formato día, mes y año del día de ejecución del código (por ejemplo, "09022024" para el 9 de febrero de 2024). Dentro de esta carpeta, se debe encontrar el archivo "import_ppa_powerbi". En la hoja "query_invoice" de este archivo, deben encontrarse los números de las Órdenes de Compra (SPO).



