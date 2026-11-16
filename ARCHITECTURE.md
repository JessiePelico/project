# Visión general de la arquitectura

La plantilla de cotización de **Pelico Servicios Eléctricos** organiza los datos de la empresa y del cliente, detalla los conceptos cotizados y presenta los importes de anticipo y saldo. Las cotizaciones guardadas se muestran como una sección aparte; el mecanismo de almacenamiento no está especificado en la información disponible.

```mermaid
flowchart TD
    Usuario["Usuario"] --> DatosEmpresa["Datos de la empresa<br/>Nombre, electricista y número"]
    Usuario --> DatosCliente["Datos del cliente<br/>Nombre, dirección, proyecto y número"]
    Usuario --> Conceptos["Conceptos de la cotización<br/>Cantidad y precio unitario"]
    DatosEmpresa --> Cotizacion["Cotización"]
    DatosCliente --> Cotizacion
    Conceptos --> Calculo["Cálculo de importes"]
    Calculo --> Cotizacion
    Calculo --> Total["Total"]
    Calculo --> Anticipo["Anticipo"]
    Calculo --> Saldo["Saldo"]
    Cotizacion --> Documento["Documento de cotización"]
    Documento --> Guardadas["Cotizaciones guardadas"]
    Guardadas -. "Persistencia no especificada" .-> Almacenamiento["Almacenamiento"]
```
