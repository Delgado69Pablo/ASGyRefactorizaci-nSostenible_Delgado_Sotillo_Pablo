# ASGyRefactorizacionSostenible_Delgado_Sotillo_Pablo

# 1. Instrucciones y Fases de la Auditoría

## **Fase 1: Inventario y Dimensión Ambiental**

### Medición inicial.
#### Website Carbon Calculator.
Para hacer la medición inicial use en primera ocasión la pagina web *Website Carbon Calculator*

<img width="1263" height="689" alt="image" src="https://github.com/user-attachments/assets/ad09e2be-e76b-4183-b7df-4a88265b7f0e" />

El rating de carbon obtinido es de clase C lo que quiere decir que los gramos de CO2 emitidos por cada visita a la paginaweb es de *0.209*

<img width="912" height="281" alt="image" src="https://github.com/user-attachments/assets/bdd9c57c-f84a-4b03-b4cb-1307f25dfc8a" />

#### Lighthouse.
Para hacer una segunda prueba acerca de las emisiones emitidas por la pagina web por cada visita hice una segunda revision en la pagina web llamada *Lighthouse* en la cual me dio los siguientes resultado:

<img width="909" height="718" alt="image" src="https://github.com/user-attachments/assets/2f833715-647a-411e-ba16-716dc373a0e0" />

Estos son los resultados que nos ofrece Lighthouse en el apartado de ordenador, pero dentro de esta extensión tambien nos permite ver como son las emisiones para moviles:

<img width="901" height="835" alt="image" src="https://github.com/user-attachments/assets/6a770876-eb6d-4b42-aa91-b2332936cb4a" />

## **Fase 2: Dimensión Social y Equidad (S).**

### Test de Accesibilidad.
Para hacer el test de accesibilidad se ha utilidado la pagina wev de *WAVE Web Accessibility Evaluation Tool* en la cual se ha copiado la URL de la pagina web y ha dado los siguientes resultados:

<img width="1919" height="946" alt="image" src="https://github.com/user-attachments/assets/23f75aeb-44e6-4e09-ab55-ca750e67e8b0" />

### Identificación de barreras.

Una vez analizado se ha detectado automaticamente una serie de 13 errores notables.
Uno de ellos era el poco contrate de colores a la hora de hacer una valoracion de la información ofrecida por la pagina web, esto podria dificultar valorizar la informacion dependiedo del dispositivo en el cual nos conectemos a la pagina web.

<img width="398" height="63" alt="image" src="https://github.com/user-attachments/assets/fa4a0e7c-7f2c-419e-94a3-b9970f41108b" />

Otro error que se ha detectado es devido a la misma causa que el error anterior;

<img width="438" height="230" alt="image" src="https://github.com/user-attachments/assets/b5204dd3-969f-4766-bf20-fee5755e4e02" />

## **Fase 3: Dimensión de Gobernanza y Ética (G)**

### Transparencia en el consentimiento de cookies
Al acceder a compramostucoche.es, aparece un banner de cookies que no facilita un rechazo claro e inmediato de las cookies no esenciales. El diseño del panel presenta varios elementos que pueden considerarse patrones oscuros (Dark Patterns) 

### Datos innecesarios en formularios
El formulario principal de tasación solicita más datos personales de los necesarios para ofrecer una estimación inicial del vehículo.
Para calcular una tasación inicial pide estos tres datos identificlables:
Email
Teléfono
Código postal

## **Fase 4: Propuesta de Refactorización (Green Coding)**

### Optimización de activos

La web puede reducir de forma notable su huella digital optimizando imágenes y recursos estáticos. Se recomienda sustituir JPG/PNG por **WebP** y **AVIF**, que reducen entre un 30% y un 60% el peso total sin pérdida de calidad. Para iconos y elementos vectoriales, se prioriza **SVG**.  
Además, la implementación de **lazy loading** evita cargar imágenes fuera del viewport, mejorando el LCP y reduciendo el consumo energético en móviles.  
Finalmente, la minificación de CSS/JS y la compresión Brotli permiten entregar recursos más ligeros y rápidos desde el servidor.

### Reducción de peticiones

La web carga varias librerías externas que incrementan el tiempo de bloqueo y el uso de CPU. Se recomienda eliminar dependencias pesadas como **jQuery** y sustituirlas por JavaScript nativo, así como reemplazar **Bootstrap completo** por CSS modular.  
Las **Google Fonts** deben sustituirse por *system fonts* para evitar peticiones externas.  
Los scripts no esenciales deben cargarse con `defer` o `async`, y los módulos opcionales (mapas, sliders, formularios avanzados) deben cargarse solo cuando el usuario los necesite.  
Estas acciones reducen el número de solicitudes y mejoran la eficiencia en dispositivos de gama baja.

### Reflexión sobre la Paradoja de Jevons

Optimizar la web hará que cargue más rápido y atraiga más usuarios, lo que podría aumentar el consumo total de energía pese a la eficiencia lograda.  
Para evitarlo, se propone cachear resultados para reducir cálculos repetidos, optimizar el backend para minimizar el uso de CPU por petición y utilizar proveedores cloud con **energía renovable**.  
También es clave monitorizar el consumo energético real y ajustar la arquitectura para que el crecimiento del tráfico no anule los beneficios ambientales obtenidos.

# 2. Refactorización. Propuesta.



