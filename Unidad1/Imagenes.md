Sí. Para una presentación Beamer generada desde Org-mode, la opción más robusta es descargar las imágenes con licencia adecuada a una carpeta local e insertarlas mediante enlaces relativos. **No conviene enlazar directamente las URL de imágenes de buscadores o medios**, porque pueden cambiar, desaparecer o no tener una licencia reutilizable para docencia.

A continuación tienes una propuesta de integración visual y los bloques Org-mode para incorporar fotografías en las diapositivas principales.

## Preparación de imágenes

Crea esta estructura junto al fichero `historia-informatica.org`:

```text
historia-informatica.org
imagenes/
├── abaco.jpg
├── quipu.jpg
├── babbage.jpg
├── ada-lovelace.jpg
├── tarjetas-perforadas.jpg
├── mark-i.jpg
├── eniac.jpg
├── valvulas-vacio.jpg
├── transistor.jpg
├── ibm-1401.jpg
├── intel-4004.jpg
├── altair-8800.jpg
├── ibm-pc-5150.jpg
├── centro-datos.jpg
└── supercomputador.jpg
```

Para evitar problemas de derechos, utiliza preferentemente imágenes de:

- Wikimedia Commons, comprobando la licencia concreta de cada archivo.
- Computer History Museum, revisando sus condiciones de uso educativo.
- Internet Archive.
- Museos universitarios y colecciones públicas.
- NASA, NIST, CERN, laboratorios nacionales y organismos públicos, según las condiciones de cada recurso.

Las fotografías históricas del ENIAC, Mark I, IBM 1401 e IBM PC 5150 ayudan especialmente a que el alumnado perciba la enorme evolución física de los equipos. Por ejemplo, una fotografía del ENIAC permite observar sus paneles, cableado y el tamaño real de la instalación; el Mark I ilustra la etapa electromecánica.

## Ajustes globales de Beamer

Añade estas líneas en la cabecera del documento Org-mode, junto al resto de `#+BEAMER_HEADER`:

```org
#+BEAMER_HEADER: \usepackage{graphicx}
#+BEAMER_HEADER: \usepackage{caption}
#+BEAMER_HEADER: \graphicspath{{imagenes/}}
#+BEAMER_HEADER: \setbeamertemplate{caption}[numbered]
```

Puedes usar estas dos formas de insertar imágenes:

```org
[[file:imagenes/eniac.jpg]]
```

O, si quieres controlar el tamaño:

```org
#+ATTR_LATEX: :width 0.78\textwidth
[[file:imagenes/eniac.jpg]]
```

Para colocar texto e imagen en dos columnas:

```org
#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.52\textwidth}
    % Texto de la diapositiva
  \end{column}
  \begin{column}{0.44\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/archivo.jpg}
  \end{column}
\end{columns}
#+END_EXPORT
```

## Diapositivas con fotografías

### Ábaco y quipu

Sustituye o amplía las diapositivas iniciales por estas versiones:

```org
** El ábaco

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.53\textwidth}
    \begin{itemize}
      \item Uno de los primeros instrumentos para realizar cálculos.
      \item Sus orígenes se remontan, al menos, al segundo milenio antes de nuestra era.
      \item Utiliza fichas o cuentas desplazables sobre varillas o líneas.
      \item Permitía realizar sumas, restas, multiplicaciones y divisiones.
      \item Representa una idea esencial: los números pueden codificarse mediante posiciones físicas.
    \end{itemize}

    \vspace{0.3cm}

    \begin{alertblock}{Idea clave}
    El ábaco no ejecuta programas, pero organiza físicamente la representación de las cantidades.
    \end{alertblock}
  \end{column}

  \begin{column}{0.43\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/abaco.jpg}

    \vspace{0.15cm}
    {\scriptsize Ábaco tradicional. Indicar fuente y licencia en la diapositiva final.}
  \end{column}
\end{columns}
#+END_EXPORT

** El quipu andino

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.47\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/quipu.jpg}

    \vspace{0.15cm}
    {\scriptsize Quipu o khipu andino.}
  \end{column}

  \begin{column}{0.50\textwidth}
    \begin{itemize}
      \item Sistema de registro basado en cuerdas, colores y nudos.
      \item Utilizado por pueblos andinos y especialmente por el Imperio inca.
      \item Permitía organizar censos, recursos, tributos e inventarios.
      \item La posición y el tipo de nudo podían codificar valores numéricos.
      \item Es un ejemplo temprano de almacenamiento estructurado de información.
    \end{itemize}

    \vspace{0.3cm}

    \begin{block}{Relación con la informática}
    Los quipus muestran que la información puede codificarse de formas distintas a la escritura alfabética.
    \end{block}
  \end{column}
\end{columns}
#+END_EXPORT
```

El quipu fue utilizado como sistema de registro mediante cuerdas y nudos por pueblos andinos, especialmente en el contexto inca; su estructura permitía codificar información administrativa y numérica.  [nist](https://www.nist.gov/nist-museum/standardizing-empire)

### Babbage y Ada Lovelace

Inserta fotografías del modelo de la máquina analítica y de Ada Lovelace. Conviene mantener la diapositiva del diagrama conceptual y añadir estas dos para humanizar y contextualizar el contenido.

```org
** Charles Babbage y la máquina analítica

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.50\textwidth}
    \begin{itemize}
      \item Charles Babbage propuso la máquina analítica en 1837.
      \item Era un diseño de máquina programable de propósito general.
      \item Incluía conceptos equivalentes a memoria, procesador, entrada y salida.
      \item Utilizaría tarjetas perforadas inspiradas en el telar de Jacquard.
      \item Nunca se completó en su época, pero anticipó la arquitectura de los computadores posteriores.
    \end{itemize}
  \end{column}

  \begin{column}{0.46\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/babbage.jpg}

    \vspace{0.15cm}
    {\scriptsize Parte construida de la máquina analítica o reconstrucción histórica.}
  \end{column}
\end{columns}
#+END_EXPORT

** Ada Lovelace: programación antes del ordenador

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.38\textwidth}
    \centering
    \includegraphics[width=0.82\linewidth]{imagenes/ada-lovelace.jpg}

    \vspace{0.15cm}
    {\scriptsize Retrato de Ada Lovelace.}
  \end{column}

  \begin{column}{0.58\textwidth}
    \begin{itemize}
      \item Ada Lovelace estudió y documentó las posibilidades de la máquina analítica.
      \item Describió un algoritmo para calcular números de Bernoulli.
      \item Comprendió que una máquina programable podría manipular símbolos y no solo números.
      \item Anticipó que una representación codificada permitiría procesar música, texto o imágenes.
    \end{itemize}

    \vspace{0.35cm}

    \begin{alertblock}{Aportación histórica}
    Ada Lovelace es considerada habitualmente la primera programadora por haber descrito un algoritmo pensado para ser ejecutado por una máquina.
    \end{alertblock}
  \end{column}
\end{columns}
#+END_EXPORT
```

### Tarjetas perforadas y Hollerith

```org
** Tarjetas perforadas: datos e instrucciones

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.52\textwidth}
    \begin{itemize}
      \item Las tarjetas perforadas permitían codificar datos e instrucciones mediante perforaciones.
      \item El telar de Jacquard demostró que una secuencia de tarjetas podía controlar un proceso automático.
      \item Herman Hollerith aplicó esta idea al procesamiento de datos del censo estadounidense de 1890.
      \item Durante décadas, las tarjetas fueron un soporte habitual para programas y datos.
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Separación entre máquina y programa}
    La misma máquina podía realizar tareas distintas simplemente cambiando la secuencia de tarjetas.
    \end{block}
  \end{column}

  \begin{column}{0.43\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/tarjetas-perforadas.jpg}

    \vspace{0.15cm}
    {\scriptsize Tarjetas perforadas utilizadas para datos o programas.}
  \end{column}
\end{columns}
#+END_EXPORT
```

### Harvard Mark I

Para esta diapositiva puedes usar como referencia visual la fotografía histórica del Mark I encontrada en la búsqueda.

```org
** Harvard Mark I: la etapa electromecánica

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.55\textwidth}
    \begin{itemize}
      \item Construido por IBM y Harvard bajo la dirección de Howard Aiken.
      \item Entró en funcionamiento en 1944.
      \item Combinaba relés, engranajes, interruptores y mecanismos motorizados.
      \item Ejecutaba secuencias de cálculos de forma automática.
      \item Su tecnología electromecánica era más lenta que la electrónica, pero permitió automatizar tareas complejas.
    \end{itemize}

    \vspace{0.25cm}

    \begin{alertblock}{Transición tecnológica}
    El Mark I representa el paso entre las calculadoras mecánicas y los computadores electrónicos basados en válvulas.
    \end{alertblock}
  \end{column}

  \begin{column}{0.41\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/mark-i.jpg}

    \vspace{0.15cm}
    {\scriptsize Harvard Mark I, 1944.}
  \end{column}
\end{columns}
#+END_EXPORT
```

El Harvard Mark I se ensambló en Harvard en 1944 y fue diseñado originalmente por Howard Aiken para abordar problemas avanzados de física matemática.  [chsi.harvard](https://chsi.harvard.edu/harvard-ibm-mark-1-about)

### Primera generación y ENIAC

La fotografía del ENIAC es especialmente útil para mostrar la escala física de los primeros computadores electrónicos.

```org
** Primera generación: válvulas de vacío

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.45\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/valvulas-vacio.jpg}

    \vspace{0.15cm}
    {\scriptsize Válvulas de vacío utilizadas en electrónica.}
  \end{column}

  \begin{column}{0.51\textwidth}
    \begin{itemize}
      \item Periodo aproximado: década de 1940 y primera mitad de los años 1950.
      \item Componente principal: válvulas de vacío.
      \item Eran grandes, frágiles y generaban mucho calor.
      \item Los computadores ocupaban salas completas.
      \item La programación se realizaba con cables, interruptores, lenguaje máquina y tarjetas perforadas.
      \item El mantenimiento era complejo debido a los fallos frecuentes de las válvulas.
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Idea fundamental}
    Las válvulas permitieron crear computadores electrónicos, mucho más rápidos que las máquinas electromecánicas.
    \end{block}
  \end{column}
\end{columns}
#+END_EXPORT

** ENIAC: un computador electrónico a gran escala

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.54\textwidth}
    \begin{itemize}
      \item ENIAC significa \textit{Electronic Numerical Integrator and Computer}.
      \item Fue desarrollado entre 1943 y 1945.
      \item Se utilizó inicialmente para cálculos balísticos.
      \item Empleaba aproximadamente 17.000 válvulas de vacío.
      \item Pesaba unas 27 toneladas y ocupaba una gran sala.
      \item Su programación requería configurar paneles y cableado.
    \end{itemize}

    \vspace{0.25cm}

    \begin{alertblock}{Relevancia}
    ENIAC demostró que la electrónica podía realizar cálculos automáticos a una velocidad muy superior a los sistemas electromecánicos.
    \end{alertblock}
  \end{column}

  \begin{column}{0.42\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/eniac.jpg}

    \vspace{0.15cm}
    {\scriptsize ENIAC con parte de su equipo de operación.}
  \end{column}
\end{columns}
#+END_EXPORT
```

El ENIAC fue concebido para responder a la necesidad de calcular tablas balísticas complejas durante la Segunda Guerra Mundial, y se convirtió en un hito de la computación electrónica a gran escala.  [computerhistory](https://www.computerhistory.org/revolution/birth-of-the-computer/4/78)

### Segunda generación: transistores e IBM 1401

La imagen de un IBM 1401 es adecuada porque muestra la estética, el tamaño y la organización física de los sistemas transistorizados empresariales.

```org
** Segunda generación: el transistor

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.49\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/transistor.jpg}

    \vspace{0.15cm}
    {\scriptsize Transistor: componente clave de la segunda generación.}
  \end{column}

  \begin{column}{0.47\textwidth}
    \begin{itemize}
      \item Periodo aproximado: mediados de los años 1950 a mediados de los años 1960.
      \item El transistor sustituyó progresivamente a las válvulas de vacío.
      \item Redujo el consumo eléctrico y el calor generado.
      \item Mejoró significativamente la fiabilidad.
      \item Permitió fabricar equipos más pequeños y rápidos.
      \item Favoreció la expansión de la informática en empresas y administraciones.
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Cambio decisivo}
    El transistor hizo que los computadores fueran más viables para el uso continuo y comercial.
    \end{block}
  \end{column}
\end{columns}
#+END_EXPORT

** IBM 1401 y la informática empresarial

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.53\textwidth}
    \begin{itemize}
      \item El IBM 1401 fue uno de los computadores transistorizados más influyentes para aplicaciones empresariales.
      \item Se utilizó en contabilidad, nóminas, inventarios y facturación.
      \item Representa la expansión de la informática fuera del ámbito estrictamente científico o militar.
      \item En esta etapa se consolidan lenguajes de alto nivel como FORTRAN y COBOL.
      \item El procesamiento por lotes seguía siendo el modelo de uso habitual.
    \end{itemize}
  \end{column}

  \begin{column}{0.43\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/ibm-1401.jpg}

    \vspace{0.15cm}
    {\scriptsize IBM 1401, ejemplo de computador transistorizado.}
  \end{column}
\end{columns}
#+END_EXPORT
```

### Años setenta, microprocesador y ejemplos en C

```org
** El microprocesador: Intel 4004

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.50\textwidth}
    \begin{itemize}
      \item En 1971 apareció el Intel 4004, uno de los primeros microprocesadores comerciales.
      \item Integraba la unidad central de procesamiento en un único chip.
      \item Era un procesador de 4 bits.
      \item Contenía aproximadamente 2.300 transistores.
      \item La integración en chips fue esencial para reducir el tamaño y el coste de los ordenadores.
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Consecuencia}
    El procesador dejó de requerir armarios de circuitos y pudo incorporarse a calculadoras, microordenadores y sistemas embebidos.
    \end{block}
  \end{column}

  \begin{column}{0.45\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/intel-4004.jpg}

    \vspace{0.15cm}
    {\scriptsize Microprocesador Intel 4004.}
  \end{column}
\end{columns}
#+END_EXPORT

** Microordenadores para aficionados

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.42\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/altair-8800.jpg}

    \vspace{0.15cm}
    {\scriptsize Altair 8800 o microordenador representativo de la década de 1970.}
  \end{column}

  \begin{column}{0.54\textwidth}
    \begin{itemize}
      \item Los microordenadores acercaron la informática a aficionados, estudiantes y pequeños negocios.
      \item Equipos como el Altair 8800 impulsaron comunidades de usuarios y programadores.
      \item Muchos se programaban en ensamblador o BASIC.
      \item Durante esta década también se consolidó el lenguaje C.
      \item El software de sistemas comenzó a desarrollarse con mayor portabilidad y organización.
    \end{itemize}

    \vspace{0.25cm}

    \begin{alertblock}{Conexión con el código C}
    Los programas en C permitían expresar algoritmos de forma más legible que el ensamblador y mantener un alto nivel de eficiencia.
    \end{alertblock}
  \end{column}
\end{columns}
#+END_EXPORT
```

El Intel 4004 se lanzó en 1971 como microprocesador de 4 bits y con unos 2.300 transistores; esta miniaturización impulsó la transición hacia los microordenadores.  [cs.cmu](https://www.cs.cmu.edu/~15292/assets/slides/10-PersonalComputer.pdf)

### IBM PC y el ordenador personal

Puedes emplear una fotografía de un IBM PC 5150, como la mostrada en los resultados visuales.

```org
** IBM PC: la expansión del ordenador personal

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.50\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/ibm-pc-5150.jpg}

    \vspace{0.15cm}
    {\scriptsize IBM PC modelo 5150, presentado en 1981.}
  \end{column}

  \begin{column}{0.46\textwidth}
    \begin{itemize}
      \item IBM presentó su PC en 1981.
      \item Popularizó el ordenador personal en el ámbito empresarial.
      \item Incorporaba un procesador Intel 8088 y utilizaba MS-DOS.
      \item Su diseño favoreció el desarrollo de equipos compatibles.
      \item El PC se convirtió en una plataforma para aplicaciones ofimáticas, programación y redes locales.
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Impacto}
    El ordenador dejó de ser un recurso centralizado y comenzó a ocupar una mesa de trabajo individual.
    \end{block}
  \end{column}
\end{columns}
#+END_EXPORT
```

IBM introdujo su PC en 1981 y su arquitectura ayudó a consolidar un estándar de facto para el mercado del ordenador personal y empresarial.  [computerhistory](https://www.computerhistory.org/revolution/personal-computers/17/301)

### Computación actual y supercomputación

```org
** De los centros de cálculo a la nube

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.54\textwidth}
    \begin{itemize}
      \item Los servicios actuales se ejecutan frecuentemente en grandes centros de datos.
      \item Miles de servidores proporcionan almacenamiento, aplicaciones, redes e inteligencia artificial.
      \item La informática actual combina:
      \begin{itemize}
        \item Procesadores multinúcleo.
        \item Virtualización.
        \item Contenedores.
        \item Redes de alta velocidad.
        \item Almacenamiento distribuido.
      \end{itemize}
    \end{itemize}

    \vspace{0.25cm}

    \begin{block}{Cambio de modelo}
    Muchas aplicaciones ya no se ejecutan exclusivamente en el equipo del usuario: utilizan recursos remotos de la nube.
    \end{block}
  \end{column}

  \begin{column}{0.42\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/centro-datos.jpg}

    \vspace{0.15cm}
    {\scriptsize Centro de datos moderno.}
  \end{column}
\end{columns}
#+END_EXPORT

** Supercomputadores: cálculo a escala exascala

#+BEGIN_EXPORT latex
\begin{columns}[T,onlytextwidth]
  \begin{column}{0.48\textwidth}
    \centering
    \includegraphics[width=\linewidth]{imagenes/supercomputador.jpg}

    \vspace{0.15cm}
    {\scriptsize Instalación de supercomputación.}
  \end{column}

  \begin{column}{0.48\textwidth}
    \begin{itemize}
      \item Un supercomputador integra miles de nodos de procesamiento.
      \item Ejecuta tareas en paralelo para resolver problemas complejos.
      \item Se utiliza en meteorología, investigación médica, simulación física e inteligencia artificial.
      \item La escala exascala supera \(10^{18}\) operaciones de coma flotante por segundo.
      \item El rendimiento depende del procesador, la memoria, la red, el almacenamiento y el algoritmo.
    \end{itemize}

    \vspace{0.25cm}

    \begin{alertblock}{Escala actual}
    Los sistemas de la lista TOP500 ya superan los dos exaFLOPS en la prueba HPL.
    \end{alertblock}
  \end{column}
\end{columns}
#+END_EXPORT
```

La clasificación TOP500 de junio de 2026 situó a LineShine como el sistema líder en rendimiento HPL, con aproximadamente 2,198 exaFLOPS; El Capitan figuraba en la segunda posición y Frontier entre los sistemas líderes.  [top500](https://top500.org/lists/top500/2026/06/)

## Diapositiva de créditos

Añade una última diapositiva antes de las fuentes textuales. Debes completar las licencias y URL exactas según los archivos que descargues.

```org
* Créditos de imágenes

** Imágenes utilizadas

#+BEGIN_EXPORT latex
\scriptsize

\begin{itemize}
  \item Ábaco: [autor, institución o colección]. Licencia: [licencia].
  \item Quipu: [autor, museo o colección]. Licencia: [licencia].
  \item Máquina analítica de Babbage: [autor, museo o colección]. Licencia: [licencia].
  \item Ada Lovelace: [autor o colección]. Dominio público o licencia: [licencia].
  \item Tarjetas perforadas: [autor, archivo o museo]. Licencia: [licencia].
  \item Harvard Mark I: [Harvard / museo / archivo]. Licencia: [licencia].
  \item ENIAC: [archivo o museo]. Licencia: [licencia].
  \item IBM 1401: [archivo, museo o colección]. Licencia: [licencia].
  \item Intel 4004: [fabricante, museo o colección]. Licencia: [licencia].
  \item IBM PC 5150: [museo o colección]. Licencia: [licencia].
  \item Centro de datos: [autor o banco de imágenes]. Licencia: [licencia].
  \item Supercomputador: [centro de investigación o institución]. Licencia: [licencia].
\end{itemize}
#+END_EXPORT

- Priorizar imágenes de dominio público, Creative Commons o con permiso educativo.
- Mantener la atribución requerida junto a la imagen o en esta diapositiva final.
```

## Recomendación didáctica y estética

Para mantener una presentación clara, evita incluir una fotografía en cada diapositiva. Una distribución equilibrada sería:

| Bloque | Imágenes recomendadas |
|---|---:|
| Orígenes | Ábaco y quipu |
| Cálculo mecánico | Babbage, Ada Lovelace y tarjetas perforadas |
| Etapa electromecánica | Harvard Mark I |
| Primera generación | Válvula de vacío y ENIAC |
| Segunda generación | Transistor e IBM 1401 |
| Años setenta | Intel 4004 y Altair 8800 |
| PC | IBM PC 5150 |
| Actualidad | Centro de datos y supercomputador |

Usa fotografías en unas 10–12 diapositivas y reserva el resto para esquemas, tablas, líneas temporales y código. Así las imágenes apoyan la explicación sin convertir la presentación en una sucesión de fotografías.