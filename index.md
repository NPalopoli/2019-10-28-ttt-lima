---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
country: pe      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: es     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
humandate: Oct 28-29, 2019    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: 9:30 am - 5:30 pm    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-10-28      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-10-29        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Nicolás Palopoli", "Rayna Harris", "Karen Word"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Layla Hirsch (host)"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["nicopalo@gmail.com"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad: https://pad.carpentries.org/2019-10-28-ttt-lima            # optional: URL for the workshop Etherpad if there is one
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
locations:
  - venue: "Pontificia Universidad Catolica del Peru (PUCP)"
    address: "Av. Universitaria 1801, San Miguel, Pabellón V, 2do piso, Lima, Peru"
    latlng: "-12.068602, -77.078058"

---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">Información General</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
  El curso está dirigido a quienes tengan
  interés en convertirse en mejores docentes. En particular, este entrenamiento
  a personas que quieran certificarse como Instructor(a) de <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.lc_site }}">Library Carpentry</a> y <a href="{{ site.dc_site }}">Data Carpentry</a>,
  ofrecer talleres y contribuir con el material de entrenamiento de The Carpentries.
  No es necesario que seas instructor o docente para participar de este taller,
  pero sí que tengas la intención y el compromiso de serlo
  y de mejorar tus técnicas de enseñanza.
</p>

<p>
  La misión de <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.dc_site }}">Data Carpentry</a> y
  <a href="{{ site.lc_site }}">Library Carpentry</a> es 
  ayudar a científicos, investigadores y bibliotecarios a investigar más en menos tiempo
  y con menos sufrimiento, enseñándoles habilidades básicas de laboratorio para la computación
  científica. Este taller práctico de dos días cubre los fundamentos de
  psicología educacional y diseño instruccional, y examina cómo
  usar estas ideas tanto en talleres intensivos como en clases regulares.
</p>
<p>
  El taller es una mezcla de ponencias y lecciones prácticas donde 
  practicarás cómo dar una pequeña lección usando los enfoques aprendidos e
  implementarás algunas de las técnicas educativas que discutiremos.
  Esto es entrenamiento para enseñar, no entrenamiento técnico: no
  necesitas ninguna formación técnica particular, y no estaremos
  enseñando eso. Este taller se basa en el <a href="{{ site.training_site }}">curriculum</a>
  revisado y actualizado permanentemente.
</p>

<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Dónde</h3>

{% assign inperson = "false" %}
{% for loc in page.locations %}

{% capture online %}{{ loc.venue | downcase }}{% endcapture %}

<h4>{{ loc.venue }}</h4>

{% if online == "online" %}

This is an online event. We will meet using the online videoconference software Zoom. You will need to <a href="https://zoom.us/download">download and install their client</a> to connect with your instructors. The link to use for this event is <{{ loc.address }}>.

{% else %}
{% assign inperson = "true" %}
{{ loc.address }} {% if loc.latlng %} Indicaciones sobre cómo llegar a la sede del curso con 
    <a href="//www.openstreetmap.org/?mlat={{loc.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
    o 
    <a href="//maps.google.com/maps?q={{loc.latlng}}">Google Maps</a>. {% endif %}

{% endif %}
{% endfor %}

{% if inperson == "true" %}

<h4 id="accessibility">Accesibilidad</h4>

Estamos comprometidos a hacer este taller accesible para todos y todas. Proveeremos el material del taller con antelación
y tendremos impresiones en tamaño grande si notificas a los organizadores por adelantado. Si necesitas asistencia o podemos 
facilitarte el aprendizaje de algún modo (por ejemplo atendiendo a tus requerimientos de movilidad, dietarios, etc), 
por favor ponte en contacto con los organizadores (usando los datos presentados más abajo) e intentaremos ayudarte.

{% endif %}

<h3>Inscripción</h3>

Por favor, completa el siguiente <a href="https://forms.gle/JAbA26BCTZxp8RVU7">Formulario de inscripción</a> para registrarte al taller.
Sólo utilizaremos tus datos para comunicar novedades respecto de esta actividad.

<h3>Requerimientos</h3>

Las y los participantes deberían llevar una computadora portátil con conexión a Internet y un
navegador funcional. Si lo tienes, también es útil llevar un dispositivo para grabar audio y video
(teléfonos móviles y computadoras portátiles son suficientes), pues durante los dos días del taller
nos grabaremos enseñando en grupos de dos o tres estudiantes. No es necesario que sean de
alta calidad, pero deberían ser suficientemente buenos para que puedas entender lo que
alguien está diciendo.

Por favor, recuerda que luego de terminar el curso, te pediremos que hagas
tres pequeños ejercicios online de seguimiento para así finalizar tu calificación
como instructor: los detalles están disponibles en
<a href="{{ site.training_site }}/checkout/">{{ site.training_site }}/checkout/</a>.
Si tienes dudas sobre el taller, el material de lectura
o cualquier otra cosa, por favor ponte en contacto.

<h3>Código de Conducta</h3>

Requerimos que todo y toda participante cumpla con el <a href="{{site.swc_site }}/conduct/">Código de Conducta</a>
de The Carpentries.

<h3 id="contact">Contacto</h3>
<p>
Por favor envía un email a
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      o
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
para más información.
</p>

<hr/>

<h2 id="preparation" name="preparation">Preparación</h2>

<p>
  Por favor lee lo siguiente antes de comenzar el taller (el contenido está en inglés):
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">La Ciencia del Aprendizaje (The Science of Learning)</a></li>
  <li><a href="https://carpentries.org/files/assessment/TheCarpentries2018AnnualReport.pdf">El Informe Anual de The Carpentries</a></li>
</ol>
<p>
  Por favor, también lee con atención <em>un</em> episodio a elección de alguna de las lecciones de The Carpentries mencionadas debajo,
  para que puedas hacer ejercicios basados en éste durante el primer día de nuestras clases. 
  Un episodio es una página de una lección.
</p>

<div class="row">
  <div class="col-md-6">
    <p><strong>Data Carpentry & Software Carpentry en español</strong></p>
    <ul>
      <li><a href="https://swcarpentry.github.io/shell-novice-es/03-create/">La Terminal de Unix: Trabajando con archivos y directorios</a></li>
      <li><a href="https://swcarpentry.github.io/git-novice-es/04-changes/">El Control de Versiones con Git: Rastreando Cambios</a></li>
      <li><a href="https://swcarpentry.github.io/r-novice-gapminder-es/05-data-structures-part2/">R para Análisis Científicos Reproducibles: Explorando data frames</a></li> 
      <li><a href="https://datacarpentry.org/python-ecology-lesson-es/02-starting-with-data/index.html">Análisis y visualización de datos usando Python: Comenzando con datos</a></li> 
    </ul>
  </div>
  <div class="col-md-6">
    <p><strong>Data Carpentry & Software Carpentry en inglés</strong></p>
    <ul>
      <li><a href="{{ site.dc_site }}/sql-ecology-lesson/01-sql-basic-queries">Basic Queries in SQL</a></li>
      <li><a href="{{ site.dc_site }}/R-ecology-lesson/02-starting-with-data.html">Starting with Data in R</a></li>
      <li><a href="{{ site.dc_site }}/python-ecology-lesson/01-starting-with-data">Starting with Data in Python</a></li>
      <li><a href="{{ site.swc_pages }}/shell-novice/03-create/">Working with Files and Directories in the Unix Shell</a></li>
      <li><a href="{{ site.swc_pages }}/git-novice/04-changes/">Tracking Changes in Git</a></li>
      <li><a href="{{ site.swc_pages }}/python-novice-inflammation/02-loop/">Repeating Actions with Loops in Python</a></li>
      <li><a href="{{ site.swc_pages }}/r-novice-gapminder/05-data-structures-part2/">Exploring Data Frames in R</a></li>
    </ul>
  </div>
</div>
  

<hr/>

<h2 id="materials" name="materials">Material de estudio y Cronograma</h2>

<p>
  Por favor, revisa <a href="{{ site.training_site }}">éste sitio</a> para obtener el material del curso y el cronograma tentativo.
</p>


<!--

<div class="row">
  <div class="col-md-6">
    <h3>Day 1</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome </td> </tr>
      <tr> <td>09:15</td> <td>How Learning Works: The Importance of Practice </td> </tr>
      <tr> <td>10:20</td> <td>How Learning Works: Expertise and Instruction </td> </tr>
      <tr> <td>11:10</td> <td>Morning Coffee </td> </tr>
      <tr> <td>11:25</td> <td>How Learning Works: Working Memory and Cognitive Load </td> </tr>
      <tr> <td>12:15</td> <td>Building Teaching Skill: Getting Feedback </td> </tr>
      <tr> <td>12:35</td> <td>Lunch </td> </tr>
      <tr> <td>13:35</td> <td>Creating a Positive Learning Environment: Motivation and Demotivation </td> </tr>
      <tr> <td>14:40</td> <td>Creating a Positive Learning Environment: Mindset </td> </tr>
      <tr> <td>15:20</td> <td>Afternoon Coffee </td> </tr>
      <tr> <td>15:35</td> <td>Building Teaching Skill: The Importance of Practice </td> </tr>
      <tr> <td>16:45</td> <td>Wrap-Up and Homework for Tomorrow </td> </tr>
      <tr> <td>17:05</td> <td>Finish </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Day 2</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome Back </td> </tr>
      <tr> <td>09:10</td> <td>Building Teaching Skill: Lesson Study </td> </tr>
      <tr> <td>10:05</td> <td>Building Teaching Skill: Live Coding </td> </tr>
      <tr> <td>11:05</td> <td>Morning Coffee </td> </tr>
      <tr> <td>11:20</td> <td>Building Teaching Skill: Performance Revised </td> </tr>
      <tr> <td>12:00</td> <td>Lunch </td> </tr>
      <tr> <td>13:00</td> <td>The Carpentries: Workshop Introductions </td> </tr>
      <tr> <td>14:10</td> <td>The Carpentries: How We Operate </td> </tr>
      <tr> <td>15:15</td> <td>Afternoon Coffee </td> </tr>
      <tr> <td>15:30</td> <td>The Carpentries: Teaching Practices </td> </tr>
      <tr> <td>16:00</td> <td>Afternoon Wrap-Up </td> </tr>
      <tr> <td>16:45</td> <td>Finish </td> </tr>
    </table>
  </div>
</div>

-->

<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}

<p id="etherpad">
  Utilizaremos el siguiente Etherpad para conversar, tomar notas, y compartir URLs y fragmentos de código.
  <br/>
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Encuestas</h2>

<p>
  Antes de participar del taller, por favor completa <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">nuestra encuesta previa</a>.
</p>


<p>
  Luego del taller, por favor completa <a href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">nuestra encuesta de finalización</a>.
</p>

<hr/>
