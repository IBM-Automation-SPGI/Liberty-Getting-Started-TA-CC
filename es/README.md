# Asesor de Transformación: Introducción al Descubrimiento de Código Común

![banner](./images/media/image1.jpeg)

**Duración:** 60 minutos

¿Necesitas ayuda? Contacta con **Yi Tang** y **Kevin Postreich.**

## Introducción a Transformation Advisor - Common Code Discovery

Este laboratorio destaca la capacidad de IBM Cloud Transformation Advisor (TA) para obtener una estimación del costo total de modernizar todas las aplicaciones en el espacio de trabajo de TA, teniendo en cuenta el código común (compartido) incluido en todas las aplicaciones, que solo necesita actualizarse una vez.

IBM Cloud Transformation Advisor (TA), una herramienta de modernización de aplicaciones incluida en IBM Cloud Pak for Applications (CP4Apps), tiene la gran capacidad de evaluar y ayudar a implementar rápidamente aplicaciones Java EE locales para su implementación en Liberty y nubes basadas en contenedores.

TA ofrece una forma completamente nueva de visualizar sus datos con su **vista a nivel de espacio de trabajo.** Esta vista muestra el esfuerzo de desarrollo estimado para modernizar todas las aplicaciones en el espacio de trabajo de TA, considerando todo el código común a todas sus aplicaciones.

Con esta capacidad, en los casos en que las aplicaciones comparten código común o archivos jar de utilidades, es fácil ver que el costo promedio para modernizar las aplicaciones puede ser significativamente menor en comparación con analizar cada aplicación de forma aislada.

Esto hace que sea más fácil ver dónde su esfuerzo de modernización generará el mayor retorno de la inversión (ROI).

Uno de los principales desafíos de la modernización de aplicaciones es obtener una estimación precisa del esfuerzo necesario para modernizar un espacio de trabajo con múltiples aplicaciones que podrían estar asociadas entre sí.

**Los equipos de desarrollo deben considerar dos aspectos:**

- ¿Qué código necesita modernizarse solo una vez (porque se usó en múltiples aplicaciones)?

- ¿Cuál es la reducción de esfuerzo para resolver los mismos problemas que se repiten en muchas aplicaciones?

Este es un proceso complejo y que requiere mucho tiempo, y puede resultar muy difícil lograr una estimación precisa de los cambios en el código y el esfuerzo requerido.

Para resolver estas preocupaciones complejas, el proceso de análisis de Transformation Advisor descubre código común en la aplicación para proporcionar un análisis preciso del esfuerzo general para modernizar las aplicaciones en el espacio de trabajo.

**El código común puede ser:**

- archivos jar de bibliotecas compartidas (código común definido por el cliente)

- archivos jar que existen en diferentes aplicaciones (código común descubierto dinámicamente).

TA utiliza una combinación de nombre de archivo y suma de comprobación para garantizar que el código común descubierto dinámicamente sea realmente común. Una vez modernizado el código común, se moderniza para todas las aplicaciones que lo utilizan. Esto significa que el esfuerzo real necesario para modernizar el espacio de trabajo será significativamente menor de lo que podría parecer al analizar cada aplicación individualmente.

TA aplica el concepto de un **costo base** y **un costo de instancia** en todos los problemas a nivel de espacio de trabajo, junto con un mecanismo de límite para los casos donde hay miles de instancias.

Se basa en el supuesto de que el mismo equipo modernizará todo el código en el espacio de trabajo, por lo que el mismo problema que aparece en cada aplicación tendrá su costo base (normalmente alto) aplicado solo una vez para el espacio de trabajo y su costo de instancia (normalmente mucho más bajo) aplicado muchas veces.

El esfuerzo general para modernizar el espacio de trabajo es el esfuerzo por **modernizar el código común** , más el esfuerzo por **modernizar el código exclusivo de las aplicaciones individuales** .

Las pruebas de clientes de TA muestran una reducción típica en el esfuerzo de modernización de alrededor del 70 % en comparación con el esfuerzo aparente del enfoque centrado en la aplicación.

## Contexto empresarial

Usted es arquitecto en su equipo de desarrollo y está planeando trasladar su aplicación Java existente, ACME, a Liberty y una nube basada en contenedores.

La aplicación ACME tiene varios módulos y usted utiliza TA para evaluar el esfuerzo de modernización de la aplicación necesario para migrar la aplicación ACME a Liberty y RedHat OpenShift.

Sabe que es extremadamente difícil obtener una estimación precisa del esfuerzo requerido. Desea utilizar Transformation Advisor, con su descubrimiento de código común y la vista del espacio de trabajo, para obtener una estimación práctica y realista del esfuerzo basándose en el análisis y la información obtenida del TA. Después, informe al equipo de desarrollo para elaborar un plan de modernización para su aplicación empresarial ACME.

  <br>


## Accediendo al entorno

Si realiza este laboratorio como parte de un taller impartido por un instructor (virtual o presencial), ya se le ha proporcionado un entorno. El instructor le proporcionará los detalles para acceder al laboratorio.

De lo contrario, deberá reservar un entorno para el laboratorio. Puede obtenerlo aquí. Siga las instrucciones en pantalla para la opción " **Reservar ahora** ".

[https://techzone.ibm.com/collection/libery-getting-started-labs](https://techzone.ibm.com/collection/libery-getting-started-labs)

El entorno de laboratorio contiene una (1) máquina virtual Linux, denominada Workstation.

<kbd><img src="./images/media/workstation.png" alt=""></kbd>

<br>

1. Acceda al entorno de laboratorio desde su navegador web.

    Se configura un `Published Service` para proporcionar acceso a la máquina virtual **`Workstation`** a través de la interfaz noVNC para el entorno de laboratorio.

    a. Cuando se aprovisione el entorno de demostración, haga clic en el **`environment tile`** para abrir su vista de detalles.

    b. Haga clic en el enlace **`Published Service`** que mostrará una **lista del directorio.**

    c. Haga clic en el enlace **`vnc.html`** para abrir el entorno de laboratorio a través de la interfaz **noVNC** .

    <kbd><img src="./images/media/vnc-link.png" alt=""></kbd>

    d. Haga clic en el botón **`Connect`**

    <kbd><img src="./images/media/vnc-connect.png" alt=""></kbd>

    e. Ingrese la contraseña: **`IBMDem0s!`** Luego, haga clic en el botón **`Send Credentials`** para acceder al entorno de laboratorio.

    > Nota: ¡Eso es un cero numérico en IBMDem0s!

    <kbd><img src="./images/media/vnc-password.png" alt=""></kbd>

     <br>
    

2. Si se le solicita iniciar sesión en la máquina virtual de la "estación de trabajo", utilice las credenciales a continuación:

    Las credenciales de inicio de sesión para la **estación de trabajo "** VM" son:

    - ID de usuario: **techzone**

    - Contraseña: **IBMDem0s!**

    > Nota: Eso es un cero numérico en la contraseña.

     <br>


    <kbd><img src="./images/media/techzone-user-pw.png" alt="pantalla de vm del estudiante"></kbd>

     <br>
    

## Consejos para trabajar en el entorno de laboratorio

1. Puede cambiar el tamaño del área visible utilizando las opciones **de configuración de noVNC** para cambiar el tamaño del escritorio virtual para que se ajuste a su pantalla.

    a. Desde la máquina virtual del entorno, haga clic en el **icono de giro** en el panel de control noNC para abrir el menú.

    <kbd><img src="./images/media/z-twisty.png" alt="ajustar a la ventana"></kbd>

    b. Para aumentar el área visible, haga clic en `Settings > Scaling Mode` y configure el valor en `Remote Resizing`

    <kbd><img src="./images/media/z-remote-resize.png" alt="ajustar a la ventana"></kbd>

2. Puede copiar/pegar texto de la guía de laboratorio en el entorno de laboratorio utilizando el portapapeles en el visor noVNC.

    a. Copie el texto de la guía de laboratorio que desea pegar en el entorno de laboratorio.

    b. Haga clic en el icono **del Portapapeles** y **pegue** el texto en el portapapeles de noVNC.

    <kbd><img src="./images/media/paste.png" alt="ajustar a la ventana"></kbd>

    c. Pegue el texto en la máquina virtual, como en una ventana de terminal, una ventana del navegador, etc.

    d. Haga clic en el icono **del portapapeles** nuevamente para cerrarlo.

3. Como alternativa a la opción "Copiar y pegar" de noVNC, puede considerar abrir la guía de laboratorio en un navegador web dentro de la máquina virtual. Con este método, puede copiar y pegar fácilmente texto de la guía de laboratorio sin tener que usar el portapapeles de noVNC.

<!-- LBH: Added description how to access toolbar -->

1. Haga clic en el ícono **`Activities`** dentro de la máquina virtual para cambiar entre diferentes ventanas u obtener acceso a la barra de herramientas. <kbd></kbd>![ajustar a la ventana](./images/media/Activies.png)<br>

# Parte 1: Cargar datos de WebSphere Application Server en TA

En este laboratorio, trabajará con un archivo de recopilación de datos generado a partir de recopilaciones de datos de TA de tres (3) entornos de WebSphere Application Server. En conjunto, estas aplicaciones representan una parte de una vista empresarial de las aplicaciones Java que se ejecutan en WebSphere en el centro de datos.

Usando la consola de TA, podría cargar las tres colecciones de datos individualmente a un espacio de trabajo de TA. Sin embargo, en este laboratorio, presentamos una opción alternativa para realizar una **carga masiva** de las tres colecciones a la vez.

La carga masiva solo está disponible como API REST en TA. La API requiere que los tres archivos zip de recopilación de datos individuales, generados desde los distintos servidores WebSphere, se agreguen a un único archivo zip. La API de carga masiva carga todas las recopilaciones de datos dentro del archivo zip maestro, lo que ahorra tiempo cuando hay muchas recopilaciones de datos para cargar en TA.

El archivo de recopilación de datos de carga masiva de WebSphere Application Server ya se ha creado para el laboratorio. Está almacenado en un repositorio de GitHub.

Además, este laboratorio utiliza TA local, que ya está instalado en la máquina virtual **de la estación de trabajo** .

En esta sección del laboratorio, clonará el repositorio de GitHub en el entorno **de la estación de trabajo** , iniciará TA localmente y cargará los datos masivos de WebSphere Application Server en TA local mediante la API de carga masiva de TA.

1. Clonar artefactos de demostración de GitHub

    a. Utilice el ícono **Actividades** para cambiar a la barra de herramientas, luego haga clic en el ícono **Terminal** para abrir una ventana de Terminal.

    <!-- LBH: Updated description how to access toolbar -->

    <kbd><img src="./images/media/Toolbar_terminal.png" alt=""></kbd>

    b. Clone el repositorio de GitHub ejecutando los siguientes comandos desde la ventana del terminal.

    <!-- LBH: Adjusted lab to use Student folder instead of home to store content -->

    ```
    mkdir /home/techzone/Student

    cd /home/techzone/Student

    git clone https://github.com/IBMTechSales/appmod-pot-labfiles
    ```

    Una vez completado, el repositorio de artefactos de laboratorio local se clona en el siguiente directorio en la máquina virtual de escritorio.

    > **/inicio/techzone/Estudiante/appmod-pot-labfiles**

    El archivo de datos masivos, **bulk_data_3.zip** , se encuentra en:

    > /inicio/techzone/Estudiante/appmod-pot-labfiles/labs/TransformationAdvisor

2. Iniciar TA Local.

    a. TA Local debe iniciarse utilizando los siguientes comandos y selecciones:

    ```
    cd /home/techzone/transformation-advisor-local-3.9.0

    ./launchTransformationAdvisor.sh
    ```

    b. Escriba **`5`** para iniciar Transformation Advisor y presione **`Enter`** .

    <kbd><img src="./images/media/image9_new.png" alt=""></kbd>

    Esto inicia el Asesor de Transformación. Tras iniciar TA Local, se proporciona la URL de la consola de TA: **http://rhel9-base.gym.lan:3000** .

    <!-- LBH: Adjusted URL as it changed -->

    <kbd><img src="./images/media/TA_has_started.png" alt=""></kbd>

3. Cargar datos masivos de WebSphere Application Server a TA Local.

    Una vez que TA Local esté listo, ejecute el `curl command` que se muestra a continuación para llamar a la API “ **bulkImport”** de TA para cargar los datos masivos de WebSphere Application Server en TA Local.

    a. Cargue el **archivo bulk_data_3.zip** con el siguiente comando en una ventana de terminal en la máquina virtual **de la estación de trabajo** :

    ```
    curl -v -k -X POST "http://rhel9-base.gym.lan:2220/lands_advisor/advisor/v2/collectionArchives/bulkImport" -H "accept: */*" -H "archiveName: bulk_data_3.zip" -H "Content-Type: application/octet-stream" --data-binary "@/home/techzone/Student/appmod-pot-labfiles/labs/TransformationAdvisor/bulk_data_3.zip"
    ```

    - Las API REST de TA se exponen a través del punto final “ **lands_advisor/advisor/v2** ” en **el puerto 2220.**

    - La importación masiva se invoca a través de **POST http** y los encabezados http necesarios

    - El **nombre del archivo de** recopilación de datos y **la ruta** al archivo “bulk_data_3.zip” se pasan como parámetros a la API

    Al invocar la API bulkImport, el comando regresa inmediatamente. Sin embargo, el proceso de importación masiva tarda unos minutos en completarse. El resultado es el siguiente:

    **Salida del comando curl:**

    ```
    curl -v -k -X POST "http://rhel9-base.gym.lan:2220/lands_advisor/advisor/v2/collectionArchives/bulkImport" -H "accept: */*" -H "archiveName: bulk_data_3.zip" -H "Content-Type: application/octet-stream" --data-binary "@/home/techzone/Student/appmod-pot-labfiles/labs/TransformationAdvisor/bulk_data_3.zip"

    Note: Unnecessary use of -X or --request, POST is already inferred.
    *   Trying 192.168.252.2:2220...
    * Connected to rhel9-base.gym.lan (192.168.252.2) port 2220 (#0)
    > POST /lands_advisor/advisor/v2/collectionArchives/bulkImport HTTP/1.1
    > Host: rhel9-base.gym.lan:2220
    > User-Agent: curl/7.76.1
    > accept: */*
    > archiveName: bulk_data_3.zip
    > Content-Type: application/octet-stream
    > Content-Length: 4460706
    > Expect: 100-continue
    >
    * Mark bundle as not supporting multiuse
    < HTTP/1.1 100 Continue
    < Content-Length: 0
    < Date: Tue, 26 Mar 2024 09:39:47 GMT
    * We are completely uploaded and fine
    * Mark bundle as not supporting multiuse
    < HTTP/1.1 200 OK
    < Date: Tue, 26 Mar 2024 09:39:47 GMT
    < Cache-Control: no-store
    < Pragma: no-cache
    < X-Content-Type-Options: nosniff
    < Content-Type: application/json
    < Content-Language: en-US
    < Content-Length: 165
    <
    * Connection #0 to host rhel9-base.gym.lan left intact
    {"message":"Bulk upload started. Track the status at: http://rhel9-base.gym.lan:2220/lands_advisor/advisor/v2/collectionArchives/bulkImport/status/344199541317364 "}
    ```

    **Nota** : La ID será diferente en su entorno.

4. La carga tardará unos minutos (3-5 minutos) en completarse.

    Puede seguir el progreso de la carga utilizando el comando que se muestra al final de la salida “bulkImport” en la ventana del terminal.

    **Ejemplo:** utilice el ícono **de Actividades** para cambiar a la barra de herramientas, luego haga clic en el ícono **de Firefox** para abrir una ventana del navegador. <kbd></kbd>![](./images/media/Toolbar_firefox.png)

    Desde el navegador web, acceda a la página de estado a través de una URL similar a esta:

    http://rhel9-base.gym.lan:2220/lands_advisor/advisor/v2/collectionArchives/bulkImport/status/344199541317364

    **Nota** : Su URL será diferente al ejemplo que se muestra, ya que la URL del estado es específica para cada bulkImport, que incluye una **ID única** para el bulkImport.

    Recargue la página de estado repetidamente hasta que vea el mensaje " **Carga masiva completada".**

    <kbd><img src="./images/media/TA_Bulk_Status.png" alt=""></kbd>

    **Nota:** También puedes seguir el progreso de la carga siguiendo los registros del contenedor Docker **de taserver** .

    Cuando se detiene el registro, es una indicación de que se ha completado la carga del archivo de recopilación de datos y puede continuar a la siguiente sección.

    ```
    docker logs -f taserver
    ```

# Parte 2: Evaluar los datos del servidor de aplicaciones WebSphere

## 2.1 Revise la información de resumen del espacio de trabajo en TA

Una vez que se completa el procesamiento de carga masiva de datos, se crea un **espacio de trabajo** en TA llamado " **ta300_data_3".**

1. Abra el nuevo espacio de trabajo en la consola TA

    a. Abra la ventana del navegador. En la ventana del navegador web, haga clic en el **`TA Local bookmark`** para abrir la consola TA. <kbd></kbd>![](./images/media/firefox_bookmark_TA.png)

    La URL local de TA es: **http://rhel9-base.gym.lan:3000**

    Se muestra **la página de bienvenida de TA UI** y puedes ver que el espacio de trabajo **ta300_data_3** está incluido.

    <kbd><img src="./images/media/image14.png" alt="Interfaz gráfica de usuario, aplicación, Teams Descripción generada automáticamente"></kbd>

2. Haga clic en el enlace del espacio de trabajo **`ta300_data_3`** para acceder al espacio de trabajo.

    <kbd><img src="./images/media/image15.png" alt=""></kbd>

    Se muestra la página del espacio de trabajo **ta300_data_3** y se han evaluado 15 aplicaciones Java, incluidas 5 aplicaciones relacionadas con la aplicación ACME.

    TA analizó las **15 aplicaciones Java** y determinó que el costo total de modernizar todas las aplicaciones en el espacio de trabajo a WebSphere Liberty es de 97,5, lo que equivale a 6,5 días por aplicación.

    TA también proporcionó el resumen del esfuerzo de modernización del código que es **exclusivo de cada aplicación** , así como el código común entre las aplicaciones.

    En este resumen, **el costo de modernizar el código común** es de **8,5** días y **el costo de modernizar una aplicación única** es de **89,5** días.

<kbd><img src="./images/media/TA_all15Apps_WLP_Costs.png" alt=""></kbd>

```
The workspace includes analysis of applications from **three** (3) WebSphere Application Server environments, per the bulk upload.

The bulk upload operation loaded the applications into TA, each into a separate “**collection**”. The name of the collections was determined by the hostnames of the WebSphere server where the applications were running. These names can be overridden in the TA UI, if desired.

<kbd>![Graphical user interface, text, application Description automatically generated](./images/media/image18.png)</kbd>

These default collection names can be overridden in the TA UI, if desired, by using the “**edit collection**” option from the Options menu. For this lab, you will just keep the default collection names.

<kbd>![](./images/media/image19.png)</kbd>


<br/>
```

## 2.2 Revise el resumen del espacio de trabajo SÓLO para las aplicaciones ACME

En este ejercicio queremos obtener una estimación precisa necesaria para modernizar el conjunto completo de aplicaciones ACME.

Las aplicaciones ACME están en la colección “ **acme.webserver.com** ”.

TA ofrece una excelente función para crear " **Grupos** " para aplicaciones Java. Los grupos proporcionan un " **Costo total estimado del grupo",** lo que permite evaluar un subconjunto de los datos de su espacio de trabajo.

La ventaja de esto es que puede obtener fácilmente una estimación precisa para modernizar un subconjunto de las aplicaciones en el espacio de trabajo.

Creemos un nuevo grupo para las aplicaciones ACME.

1. Haga clic en el menú desplegable **`Collections`** . Luego, marque la casilla junto a **`acme.webserver.com` .** Asegúrese de que las otras dos colecciones permanezcan desmarcadas.

    <kbd><img src="./images/media/image21.png" alt=""></kbd>

2. A continuación, marque la casilla junto a la aplicación Java, lo que seleccionará las cinco aplicaciones ACME. A continuación, haga clic en **`Add to group`** .

<kbd><img src="./images/media/image23.png" alt=""></kbd>

1. Proporcione un nombre de grupo como **`ACME`** y haga clic en **`Add to group(s)` .**

    <kbd><img src="./images/media/image24.png" alt=""></kbd>

    Se ha creado un nuevo grupo llamado **ACME** , y aparece en **Grupos** en el menú de navegación de TA.

    <kbd><img src="./images/media/image25.png" alt=""></kbd>

2. Seleccione el grupo **`ACME`** en **`Groups`** , lo que hará que TA vuelva a calcular el esfuerzo involucrado para modernizar el espacio de trabajo con alcance para incluir solo el grupo de aplicaciones ACME.

    <kbd><img src="./images/media/acme-group.png" alt=""></kbd>

    Ahora ves que TA ha recalculado los costos asociados a la modernización sólo del grupo de aplicaciones ACME.

    <kbd><img src="./images/media/image27.png" alt=""></kbd>

    El **resumen del grupo ACME** ahora muestra **5 aplicaciones** y un promedio de **1,7** días para modernizar cada aplicación.

    La evaluación de TA de los costos estimados del Grupo toma en consideración lo siguiente:

    - El **código de aplicación único** que se va a modernizar, que es de **1,5** días.

    - El **código común** compartido entre algunas o todas las aplicaciones, que es de **8,5** días.

    Con esta visión, TA ha elaborado una estimación de costos realista y más precisa para modernizar la aplicación ACME.

    El costo de modernizar las **cinco** aplicaciones ACME, incluido el código común, que solo necesita actualizarse UNA VEZ, es de aproximadamente **8,5** días.

    A partir de esto, podemos ver el valor del análisis TA en términos de mirar las aplicaciones para encontrar CÓDIGO COMÚN y bibliotecas COMPARTIDAS, y luego llegar a una recomendación razonable para modernizar las aplicaciones ya que el código común solo necesita repararse una vez y está reparado para todas las aplicaciones que lo usan.

    En este ejemplo, sin descubrimiento de código común, el costo de modernización de cada aplicación individual es de **38,5** días, como se ilustra a continuación. Sin embargo, la **estimación más precisa** del **costo total** es de **8,5** días, según el análisis de TA del código común utilizado en las aplicaciones ACME.

    El coste de modernizar el **código de aplicación único** en el grupo ACME es de solo **1,5** días.

    <kbd><img src="./images/media/image29.png" alt=""></kbd>

    TA muestra la cantidad de archivos de código común que detectó y utilizó para cada aplicación.

    Transformation Advisor busca código común entre todas las aplicaciones, incluso si están en diferentes colecciones en el espacio de trabajo.

## 2.3 Explorar el descubrimiento de código común en TA

En esta sección del laboratorio, profundizará en los detalles de las aplicaciones ACME para comprender el costo de modernizar aplicaciones que comparten código. Obtendrá información sobre las bibliotecas de código común y qué aplicaciones comparten este código.

Con estos conocimientos, aprenderá qué bibliotecas de código común proporcionarían el mejor retorno de la inversión para modernizar primero, ya que solo paga por modernizar la biblioteca compartida una vez y todas las aplicaciones que usan ese código común se benefician.

1. Primero, echemos un vistazo rápido a los archivos de código común que se han descubierto en el espacio de trabajo.

    a. Desde el grupo ACME, abra la pestaña " **`Common code`** ".

    <kbd><img src="./images/media/image31.png" alt=""></kbd>

    b. Ahora verá el resumen de los archivos de código común, incluida la **complejidad, los problemas** , **los usos de las aplicaciones** y **el costo** de modernizar el archivo de código común.

    <kbd><img src="./images/media/image32.png" alt=""></kbd>

2. Regrese a la pestaña “ **`Java Applications`** ” y vea los detalles del código común utilizado por la aplicación **ACMEAnnuityEJBMDB.ear**

    a. Haga clic en la pestaña " **`Java applications`** " para volver a la lista de aplicaciones Java.

    <kbd><img src="./images/media/image33.png" alt=""></kbd>

    b. Expanda la aplicación **ACMEAnnuityEJBMDB.ear** para obtener los detalles del código común utilizado por la aplicación.

    <kbd><img src="./images/media/image34.png" alt=""></kbd>

    **Tenga en cuenta los detalles importantes sobre el costo de modernización de la aplicación y el código común.**

    - La aplicación utiliza **2** archivos jar de código común

        - AcmeAnnuityCommon.jar

        - AcmeCommon.jar

    - Ambos archivos jar de código común son utilizados por **5** aplicaciones

    - La complejidad de la modernización **de AcmeAnnuityCommon.jar** es **MODERADA**

    - La complejidad de la modernización **de AcmeCommon.jar** es **SIMPLE**

    - El costo de modernizar el **código común** es de **7,5** días

    - El costo de modernizar el **código único de la aplicación** es de **0** días (no se requieren cambios de código)

    Con esta información puedes ver que **TODO** el costo asociado para modernizar **ACMEAnnuityEJBMDB.ear** está en código común, y estos archivos de código común son utilizados por **5** aplicaciones.

    Esto significa que solo se modernizan estos archivos de código común una vez y queda solucionado para las **cinco** aplicaciones que también comparten este código común.

    c. **`Collapse`** la vista de detalles del código común para la aplicación **ACMEAnnuityEJBMDB.ear.**

3. Ahora vea los detalles del código común utilizado por la aplicación **ACMEAnnuityEJBWSes.ear** .

    a. Expanda la aplicación “ **ACMEAnnuityEJBWSes.ear”** de la lista de aplicaciones Java.

    <kbd><img src="./images/media/image37.png" alt=""></kbd>

    **Tenga en cuenta los detalles importantes sobre el costo de modernización de la aplicación y el código común.**

    - La aplicación utiliza **5** archivos jar de código común

    - El costo de modernizar el **código común** es de **7,5** días

    - El costo de modernizar el **código único de la aplicación** es de **1,5** días

4. Dado que el código común **AcmeAnnuityCommon.jar** se utiliza para las cinco aplicaciones, revisemos los detalles de modernización del mismo.

    a. Haga clic en el archivo de código común **AcmeAnnuityCommon.jar** para obtener los detalles de la modernización.

    <kbd><img src="./images/media/image40.png" alt=""></kbd>

    b. La vista de detalles del archivo **AcmeAnnuityCommon.jar** revela información y conocimientos muy importantes sobre la modernización de las aplicaciones ACME, como se ilustra a continuación.

    - **AcmeAnnuityCommon.jar** es utilizado por las **5** aplicaciones ACME

    - El costo de modernización de **AcmeAnnuityCommon.jar** es de **7,5** días.

    - Si analizamos cada aplicación de forma aislada, como se ilustra a continuación, veremos que el coste total de cada aplicación es de entre **7,5** y **8,5** días.

        - **AcmeAnnuityCommon.jar** representa **7,5** días de ese costo, pero solo es necesario incurrirlo una vez.

    - La modernización del **código de aplicación único** en las **cinco** aplicaciones lleva solo **1,5** días.

        - 1,5 días para ACMEAnnuityEJBWSes.ear

    Los conocimientos adquiridos aquí muestran claramente que realizar los **7,5** días necesarios para modernizar el archivo **AcmeAnnuityCommon.jar** significa que la MAYOR parte del trabajo se completará para las cinco (5) aplicaciones ACME.

    <kbd><img src="./images/media/image41.png" alt=""></kbd>

5. Mientras esté en la vista de detalles **de AcmeAnnuityCommon.jar** , desplácese hacia abajo para ver las aplicaciones que usan este jar de utilidad común.

    Como se señaló en el paso anterior, AcmeAnnuityCommon.jar es utilizado por las 5 aplicaciones ACME.

6. De la lista de aplicaciones que utilizan este archivo jar de utilidad de código común, `click` en la aplicación **ACMEAnnuityEJBWSes.ear** para mostrar sus detalles.

    <kbd><img src="./images/media/image41-b.png" alt=""></kbd>

7. Mientras esté en la vista de detalles **de ACMEAnnuityEJBWSes.ear** , desplácese hacia abajo hasta las secciones de **Problemas de complejidad** y **Detalles de problemas** , donde puede comenzar a profundizar en los problemas específicos marcados por TA.

    a. Tenga en cuenta que Transformation Advisor divide los detalles de los problemas en dos secciones, lo que hace que sea rápido y fácil acceder a los detalles específicos que desea revisar.

    - Problemas del Código Común

    - Problemas con el código único

    Aquí usted comienza a obtener información sobre los problemas específicos que deben abordarse y los costos asociados para resolver los problemas específicos que se descubrieron.

    <kbd><img src="./images/media/image42.png" alt=""></kbd>

    En resumen, la información obtenida con la función de descubrimiento de código común de Transformation Advisors muestra claramente que, al realizar los **8,5** días de esfuerzo necesarios para modernizar el archivo **AcmeAnnuityCommon.jar** , se completará TODO el trabajo para las cinco (5) aplicaciones ACME. Aprendió que **7,5** días de ese trabajo se destinan a modernizar el código común, lo cual solo se requiere una vez.

    Recuerde que la vista de resumen del **grupo de aplicaciones ACME** mostró que el **costo total** para modernizar todo el grupo de aplicaciones ACME es de **8,5** días.

    <kbd><img src="./images/media/image27.png" alt=""></kbd>

    <br>

## 2.3.1 Utilice la Guía de migración para ver dónde empezar

Ahora que sabe qué aplicación necesita qué esfuerzos para modernizarse, surge la pregunta de con cuál empezar. Transformation Advisor le ofrece orientación para empezar.

1. En TA, vuelva a la vista de aplicaciones Java. Haga clic en el enlace para **obtener ayuda** .

    <kbd><img src="./images/media/TA-Guidance1.png" alt="Guía TA1"></kbd>

2. Aparecerá un asistente que explica cómo usar la guía. Navega por ella haciendo clic en **Siguiente** y luego cierra el asistente.

    <kbd><img src="./images/media/TA-Guidance2.png" alt="Guía TA2"></kbd>

3. En la parte superior, verás la lista de **aplicaciones sencillas** que no requieren cambios de código. Haz clic en **"Mostrar más"** para ver todas las aplicaciones.

    <kbd><img src="./images/media/TA-Guidance3a.png" alt="TA-Orientación3a"></kbd>

4. Desplácese hacia abajo hasta la sección con **aplicaciones moderadas** .

    <kbd><img src="./images/media/TA-Guidance3b.png" alt="Guía TA3b"></kbd>

    Como puede ver, la guía recomienda comenzar con la aplicación moderada **ACMEAnnuityEJBMDB.ear** , ya que los cambios de código también afectarán a otras cuatro aplicaciones y solo un archivo jar se ve afectado. No dude en investigar más a fondo las diferentes recomendaciones.

## 2.3.2 Exportar y revisar el resumen del espacio de trabajo y los detalles de la aplicación

Para las grandes empresas, podría haber cientos de aplicaciones y miles de archivos de código común que necesiten analizarse.

Transformation Advisor brinda la posibilidad de exportar todos esos datos en archivos PDF y archivos de vista separados por comas (CSV) que pueden compartirse fácilmente entre el equipo de desarrollo.

Los archivos CSV proporcionan una forma agradable de manipular, ordenar, clasificar y visualizar el gran volumen de datos para ayudarle con la planificación real de sus proyectos de modernización.

La exportación genera un archivo zip del resumen del espacio de trabajo y/o los detalles de la aplicación según sus criterios de selección en la exportación.

1. Exportar el espacio de trabajo y los detalles de la aplicación para el grupo de aplicaciones **ACME** .

    a. En TA, regrese a la vista **de aplicaciones Java** del `ACME group` . Haga clic en el icono **`Export`** .

    <kbd><img src="./images/media/image44.png" alt=""></kbd>

    b. En la página "Exportar", asegúrese de que " **Resumen del espacio de trabajo** " y " **Detalles de la aplicación** " estén seleccionados para su exportación y, a continuación, haga clic en **`Export`** .

    <kbd><img src="./images/media/image46.png" alt=""></kbd>

    c. Acepte los valores predeterminados y haga clic en **Guardar.** <kbd></kbd>![](./images/media/image46-b.png)

    Se crea un archivo zip llamado “ **ta300_data_3_ACME_websphereLiberty_report.zip** ” en el directorio: **/home/techzone/Downloads.**

2. Desde una ventana de Terminal, descomprima (extraiga) el contenido del archivo, utilizando los siguientes comandos:

    ```
    cd /home/techzone/Downloads

    unzip ta300_data_3_ACME_websphereLiberty_report.zip -d /home/techzone/Student/ACME
    ```

3. Explore la estructura del archivo y el contenido de los datos exportados.

    a. Haga clic en **Actividades** para acceder a la barra de herramientas, luego seleccione el `File Explorer` . <kbd></kbd>![](./images/media/Toolbar_fileExplorer.png)

    b. Navegue hasta el directorio:

    ```
    Home > techzone > Student > ACME > ta300_data_3_ACME
    ```

    La estructura del archivo se divide en dos categorías, una para el resumen del espacio de trabajo y la otra para los detalles de la aplicación.

    <kbd><img src="./images/media/image47.png" alt="imagen47"></kbd>

    c. Abra el directorio **`summary`** .

    <kbd><img src="./images/media/image47-b.png" alt="imagen47-b"></kbd>

    ---

    Tenga en cuenta que los datos **de resumen del espacio de trabajo** están separados por aplicaciones, código común y reglas.

    En cada uno de los subdirectorios encontrará los archivos csv y pdf que contienen los datos de resumen

    ---

    d. Abra el directorio **`applications`** y haga doble clic en el archivo pdf para ver el resumen de aplicaciones ACME.

    <kbd><img src="./images/media/image48.png" alt="imagen48"></kbd>

    <kbd><img src="./images/media/image49.png" alt="imagen49"></kbd>

    e. Navegue al directorio **`ACME/ta300_data_3_ACME/summary/commonCode`** y abra el archivo PDF para ver el resumen del código común.

    <kbd><img src="./images/media/image50.png" alt="imagen50"></kbd>

    <kbd><img src="./images/media/image51.png" alt="imagen51"></kbd>

    Puede continuar explorando los archivos csv y pdf en las otras secciones de los datos exportados.

    Cuando esté listo, continúe con la siguiente y última sección del laboratorio, donde explorará cómo Transformation Advisor y Binary Scanner del kit de herramientas de migración de aplicaciones WebSphere trabajan juntos para la planificación y el análisis de proyectos de modernización de Java.

# Parte 3: Uso del escáner binario con TA

El kit de herramientas de migración para binarios de aplicaciones es una herramienta del kit de herramientas de migración de IBM WebSphere Application Server. Incluye la capacidad de escaneo para evaluar rápidamente los binarios de aplicaciones y así implementarlos rápidamente en WebSphere Application Server tradicional y Liberty.

Esta herramienta de línea de comandos permite a los administradores evaluar aplicaciones en minutos sin acceder al código fuente. También se puede integrar con TA y añadir datos escaneados a un espacio de trabajo de TA existente.

**El escáner binario puede escanear un binario de aplicación, como un archivo WAR o EAR.**

- Escanear un archivo binario solo produce datos de la aplicación.

**El escáner binario también puede escanear una configuración de perfil de servidor de aplicaciones WebSphere.**

- Con esta opción, el escáner binario también recopila los datos de configuración del servidor WebSphere y produce aceleradores de implementación para crear e implementar la aplicación en Liberty, WebSphere tradicional en contenedores y nubes basadas en contenedores.

**El escáner binario también se puede ejecutar utilizando la opción **`--ta`** , que produce un archivo de recopilación de datos que se puede cargar directamente en Transformation Advisor.**

- Con la opción **`--ta`** , el archivo de recopilación de datos se puede cargar en TA. Las aplicaciones se pueden analizar junto con las que ya se han cargado en la interfaz de TA. Esto permite comprender mejor las aplicaciones de la empresa, incluyendo el código común entre aplicaciones de diferentes aplicaciones WebSphere y servidores de aplicaciones.

<table>
<tbody>
<tr class="odd">
<td>
<p>El Recopilador de Datos del Asesor de Transformación (TA DC) se basa en el Kit de Herramientas de Migración de WebSphere para Binarios de Aplicaciones (también conocido como Escáner Binario) y ambos son compatibles para analizar aplicaciones que se ejecutan en WebSphere App Server. Para obtener los mejores resultados, siempre que sea posible, ejecute la última versión disponible.</p>
<p><strong>Las razones para ejecutar Binary Scanner incluyen:</strong></p>
<ul>
<li><p>Está listo para comenzar la recopilación de datos, pero aún no tiene TA instalado. Esto puede acelerar la fase de análisis, donde se puede continuar con el descubrimiento mientras se encuentra un sistema OpenShift o RHEL adecuado para instalar TA o TA Local en paralelo.</p></li>
<li><p>El escáner binario ya está integrado en WAS, se envía como parte de los paquetes de correcciones de WebSphere 9.0.5.14 o posteriores y se puede ejecutar directamente en esos sistemas sin un proceso de solicitud de cambio para agregar software adicional en los sistemas controlados.</p></li>
<li><p>Para los sistemas WAS anteriores a 9.0.5.14, el escáner binario más reciente se puede descargar desde <a href="https://www.ibm.com/support/pages/migration-toolkit-application-binaries"><span class="underline">https://www.ibm.com/support/pages/migration-toolkit-application-binaries</span></a> y ejecutar directamente en esos sistemas (o en una copia de seguridad disponible), sin tener primero instalado TA.</p></li>
</ul>
<p><strong>Las razones para utilizar TA DC incluyen:</strong></p>
<ul>
<li><p>Si TA ya está instalado pero no está en el nivel más reciente, el uso del recopilador de datos incorporado garantiza que los resultados sean compatibles para la carga.</p></li>
<li><p>El recopilador de datos de TA intenta cargar automáticamente los resultados en TA una vez finalizado</p></li>
<li><p>El recopilador de datos de TA sigue siendo necesario para analizar otros servidores de aplicaciones, como WebLogic, JBoss y Tomcat, si se requieren artefactos de migración. De lo contrario, el analizador binario puede analizar el binario de la aplicación para permitir la visualización de la evaluación en TA.</p></li>
<li><p>El escáner binario no tiene el modo --ta para WebLogic, JBoss ni Tomcat. Los informes competitivos generados por el escáner binario independiente no se pueden cargar en TA.</p></li>
</ul>
</td>
</tr>
</tbody>
</table>

### **SOLO CON FINES ILUSTRATIVOS: Simulación de la ejecución de la utilidad del escáner binario**

<table>
<tbody>
<tr class="odd">
<td><kbd><img src="./images/media/warn.png" style="width:0.60625in;height:0.60625in" alt="señal de precaución"></kbd></td>
<td>
<p><strong>Importante:</strong></p>
<p>Esta sección es sólo para fines ilustrativos.</p>
<p>¡NO EJECUTE LOS COMANDOS que se muestran en esta sección!</p>
</td>
</tr>
</tbody>
</table>

En esta sección, ejecutará el analizador binario en una configuración de perfil de servidor de aplicaciones WebSphere que tenga implementada una aplicación llamada **`PlantsByWebSphere`** . Utilizará la opción **`--ta`** y cargará el archivo de recopilación de datos resultante en el espacio de trabajo de TA.

El escáner binario es un archivo jar independiente. Ya se ha descargado en el siguiente directorio de la máquina virtual de la estación de trabajo.

> /inicio/techzone/escáner binario/wamt

La configuración del entorno de WebSphere Application Server también está disponible en la máquina virtual de la estación de trabajo en el siguiente directorio:

> /opt/IBM/WebSphere/AppServer85515

<br>

1. Ejecute el analizador binario para recopilar los datos de la aplicación **PlantsByWebSphere** en el perfil de WebSphere denominado " **perfil1** ", usando la opción **"--ta** ". **Nuevamente, NO EJECUTE el siguiente comando.**

    ```
    cd /home/techzone/binary-scanner/wamt

    java -jar binaryAppScanner.jar /opt/IBM/WebSphere/AppServer85515 --ta --profile=AppSrv01
    ```

    <kbd><img src="./images/media/image52.png" alt=""></kbd>

    El archivo de recopilación de datos generado se llama **AppSrv01.zip** y se crea en el siguiente directorio:

    > /inicio/techzone/escáner binario/wamt

    Con el archivo de recopilación de datos, **AppSrv01.zip** creado usando la opción “-- **ta”** , se puede cargar en Transformation Advisor desde la interfaz de usuario.

# Parte 4: Carga del archivo de colección creado por el escáner binario

**Consejo:** como se señaló en la sección anterior, los pasos de recopilación de datos ya se han realizado y el archivo **`AppSrv01.zip`** resultante se proporciona en el entorno de laboratorio en **`/home/techzone/Student/appmod-pot-labfiles/labs/TransformationAdvisor/AppSrv01.zip`** .

1. En la interfaz de usuario de TA, haga clic en “ **Todas las aplicaciones Java** ” para volver a la vista “ **Todas las aplicaciones Java** ”. <kbd></kbd>![](./images/media/image53-a.png)

    Las 15 aplicaciones deberían volver a mostrarse y enumerarse en el espacio de trabajo.

    <kbd><img src="./images/media/image53.png" alt=""></kbd>

2. Sube el archivo “ **AppSrv01.zip** ” a TA.

    a. Desde la interfaz de usuario de TA, haga clic en **`Options > Upload data`** en el menú **`options`** para comenzar a cargar el nuevo archivo **`AppSrv01.zip`** recopilado desde el escáner binario.

    <kbd><img src="./images/media/image55.png" alt=""></kbd>

    b. Haga clic en **`Drop or add file`** .

    <kbd><img src="./images/media/image56.png" alt=""></kbd>

    c. Vaya a **`Home > techzone > Student > appmod-pot-labfiles > labs > TransformationAdvisor`** . Seleccione **AppSrv01.zip** y haga clic **`Open`** .

    <kbd><img src="./images/media/image57.png" alt=""></kbd>

    d. Haga clic en el menú desplegable " **Detectar colección automáticamente** ".

    Esta opción le permite elegir cómo se nombrará la nueva colección cuando se cargue en TA.

    - El modo predeterminado es detectar automáticamente el nombre del archivo. Este nombre será el nombre del equipo host donde se generó el archivo de colección.

    - Puede optar por cargar la colección a una “colección existente” que ya se encuentra en el espacio de trabajo de TA.

    - Puede optar por proporcionar su propio nombre de colección único.

    <kbd><img src="./images/media/image58.png" alt=""></kbd>

    e. En este caso, simplemente acepte la opción predeterminada " **Detectar automáticamente el nombre de la colección del archivo** ". Luego, haga clic en **`Upload`** para cargar los datos.

    <kbd><img src="./images/media/image59.png" alt=""></kbd>

    Las aplicaciones Java en el servidor de aplicaciones WebSphere local se agregan al espacio de trabajo **ta300_data_3** .

    Ahora el número total de aplicaciones en el espacio de trabajo es **20** .

    <kbd><img src="./images/media/image60.png" alt=""></kbd>

3. Vea las aplicaciones Java en la nueva colección que se creó cuando se cargó **AppSrv01.zip** .

    a. Expanda la lista “Colecciones” y seleccione la nueva colección denominada **`admin.ibm.demo`** .

    <kbd><img src="./images/media/image61.png" alt=""></kbd>

    b. Revise la lista de aplicaciones de esta colección. Esta colección incluye la aplicación **CustomerOrderServicesApp** , así como otras cuatro aplicaciones que están listas para su análisis desde el espacio de trabajo.

    <kbd><img src="./images/media/image62.png" alt=""></kbd>

    <br>

    Transformation Advisor busca código común entre todas las aplicaciones, incluso si están en diferentes colecciones en el espacio de trabajo.

    A utiliza una combinación del **nombre del archivo JAR** y **la SUMA DE VERIFICACIÓN** para determinar si el archivo JAR de la biblioteca compartida es **IDÉNTICO** y realmente compartido entre aplicaciones.

    Por lo tanto, agregar la nueva colección al mismo espacio de trabajo sería beneficioso para obtener una “ **vista empresarial** ” de las aplicaciones que se están analizando.

    Las aplicaciones en diferentes servidores de aplicaciones WebSphere, que estarían en colecciones diferentes, pueden compartir código común de toda la empresa.

## Parte 5: Limpieza

1. Por último **`remove`** la carpeta **`Student's`** y los recursos descargados.

    ```
    cd ~
    rm -rf ~/Student
    rm ~/Downloads/*
    ```

2. Asesor de Detención de Transformación

    ```
     cd /home/techzone/transformation-advisor-local-3.9.0
     scripts/stopTransformationAdvisor.sh
    ```

3. Cierre el navegador y todas las ventanas de terminal.

# Resumen

¡Felicitaciones! Ha completado el laboratorio de Proceso de Código Común de IBM Transformation Advisor.

Con el análisis y los conocimientos obtenidos a través de Transformation Advisor y sus capacidades de descubrimiento de código común, es fácil obtener una estimación realista y más precisa de la modernización de un conjunto de aplicaciones que comparten un código común.

Como tal, en los casos donde se descubre un código común entre las aplicaciones en el espacio de trabajo, probablemente verá un costo total y promedio por modernización de aplicación significativamente menor en comparación con la evaluación de cada aplicación de forma aislada.

Esto hace que sea más fácil ver cómo invertir su esfuerzo de modernización para producir el retorno de la inversión óptimo para la modernización.
