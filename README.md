# Isocronas-HEMS-GC

PWA no oficial del Servicio de Urgencias Canario para consulta de isócronas del helicóptero medicalizado HEMS AH-30, base Gando, Gran Canaria. Herramienta clínica interactiva con tiempos de traslado, calculadora dinámica y funcionalidad offline para coordinadores de emergencias.

Clonada de [Isocronas-HEMS-TF](https://github.com/jaacos/Isocronas-HEMS-TF) (Tenerife), manteniendo idéntica interfaz y lógica, con paleta amarilla propia para diferenciarla de la versión de Tenerife.

## Estado: datos cargados, fase piloto

Los 21 municipios de Gran Canaria tienen:
- **Centroide poblacional** ponderado por habitante (Nomenclátor Geográfico del IGN, NGMEP, verificado uno a uno contra el padrón municipal).
- **Hospital de referencia** asignado según la sectorización oficial por Zona Básica de Salud del Servicio Canario de Salud (Hospital Insular o Dr. Negrín).
- **Tiempo de vuelo** Gando → municipio → hospital: modelo geométrico (distancia ortodrómica, velocidad crucero 243 km/h, factor de tortuosidad 1.00–1.15). **Estimación no validada por tripulación**, igual que en Tenerife — pendiente de contraste operativo si se quiere usar en publicación científica.
- **Tiempo terrestre real** base SVAm → municipio → hospital, calculado por carretera (OpenRouteService, perfil driving-car, factor de corrección por prioridad 0.85), desde las bases reales 33.90 (Hospital Negrín), 33.91 (Hospital Insular), 33.92 (ICOT Telde) y 33.93 (Centro de Salud Maspalomas).
- **Tiempo de movilización HEMS**: rango 4–7 min, confirmado igual que en AH-40.

**Artenara, La Aldea de San Nicolás y Tejeda** no tienen SVAm cercano viable según la documentación operativa del SUC — se muestra su tiempo HEMS pero no hay comparador terrestre principal. La Aldea incluye además una nota aparte (no equivalente) sobre su ambulancia SVA-e local, que puede medicalizarse in situ con el médico del centro de salud sin retraso relevante, pero de forma condicionada a disponibilidad, no como dotación fija.

## Pendiente

- Validación por tripulación del AH-30 de los parámetros del modelo de vuelo (velocidad, tortuosidad).
- Confirmación de la Zona Básica de Salud de Artenara (agrupada administrativamente con otra zona, no listada de forma independiente).
- Infraestructura oficial: si esta herramienta pasa a ser un producto oficial SUC/GSC, las decisiones de despliegue deben pasar por GSC IT.

## Fase piloto

Repositorio con `robots.txt` y meta `noindex` activos — no indexar en buscadores mientras dure la fase piloto.
