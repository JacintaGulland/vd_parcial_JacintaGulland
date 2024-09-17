<!-- Script JS -->
<script>
  /* Importamos d3 para tenerlo disponible */
  import * as d3 from "d3"

  /* Defini los datos que voy visualizar */
  let data = [21, 33, 42, 54, 63, 71, 77, 84, 92, 98]
  let años = [2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023]
  let datab = [23, 35, 45, 56, 50, 43, 38, 32, 28, 25]

  /* Escala para el color de los círculos de Di Tella basada en el valor de los datos */
  let colorLightness = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range(["white", "#4300ee"])

  /* Escala para el color de los círculos de San Andrés basada en el valor de los datos */
  let colorLightnessb = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range(["white", "#ff8800"])

   /* Escala para representar los años */
  let tiempo = d3
    .scaleLinear()
    .domain([0, d3.max(años)])

   /* Escala radial para el tamaño de los círculos */
    let scale = d3.scaleRadial()
    .domain([d3.min(data), d3.max(data)])
    .range([25, 100]);  // Radio de los círculos
</script>

<!-- Estructura contenido HTML -->
<div class="header">
  <h1 class="titulo"><b>La lucha por los alumnos</b></h1>
  <h2 class="subtitulo">Di Tella vs San Andrés</h2>
  <p class="bajada"> Desde hace más de una década, dos de las universidades más prestigiosas de Buenos Aires se encuentran en una guerra para ver cual cuenta con más inscriptos nuevos cada año. En los últimos años los cambios fueron más interesantes y grandes, definiendo mas un líder luego de muchos años de lucha pareja.
  </p>
</div>

<body>
<!-- Sección de gráficos para Di Tella -->
<h6 class="titulos">Di Tella</h6>
<div class="container_2">
  {#each data as num}
    <div class="item_wrapper">
      <div class="circle" style="background-color: {colorLightness(num)}; width:{scale(num)}px; height:{scale(num)}px "></div>
    </div>
  {/each}
</div>
<!-- Sección de gráficos para San Andrés -->
<h6 class="titulos">San Andrés</h6>
<div class="container_2">
  {#each datab as num}
    <div class="item_wrapper">
      <div class="circle" style="background-color: {colorLightnessb(num)}; width:{scale(num)}px; height:{scale(num)}px "></div>
    </div>
  {/each}
</div>
<!-- Sección de gráficos para los años -->
<div class="container_2">
  {#each años as num}
    <div class="item_wrapper">
      <p class="num_2">{num}</p>
    </div>
  {/each}
</div>

<p class="cambios">En el año 2016 la Di Tella implementó nuevos cambios en sus carreras, e incluye programas innovadores que generó un creciente interés. Agregaron carreras que solo se encontraban en San Andrés, generando que muchos alumnos ingresantes tengan la oportunidad de cursar la carrera en Di Tella.</p>

<!-- Contenedor primer grafico Flourish -->
<div class="flourish-container1">
  <iframe src='https://flo.uri.sh/visualisation/19289428/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:550px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19289428/?utm_source=embed&utm_campaign=visualisation/19289428' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
</div>

<!-- Contenedor de los otros dos gráficos de Flourish -->
<div class="flourish-container">
  <div class="chart-wrapper">
    <iframe src='https://flo.uri.sh/visualisation/19440537/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:400px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19440537/?utm_source=embed&utm_campaign=visualisation/19440537' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
  </div>

  <div class="chart-wrapper">
    <iframe src='https://flo.uri.sh/visualisation/19370611/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:400px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19370611/?utm_source=embed&utm_campaign=visualisation/19370611' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
  </div>
</div>
</body>

<footer>
  <p class="cierre"> Si San Andrés quiere volver a ser una universidad competitiva tiene que generar cambios o proponer nuevas carreras o programas para atraer más alumnos ya que desde que Di Tella implementó nuevas medidas su crecimiento fue siempre progresivo y constante. </p>
  <p class="nombre">Jacinta Gulland - Parcial Visualización de Datos</p>
</footer>

<!-- Estilos CSS -->
<style>
  @import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,200..900;1,200..900&display=swap');

body {
    font-family: 'Source Sans 3', sans-serif;
    color: #7a7a7a;
}
  .header {
    /* Centra el contenido dentro del contenedor */
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin-top: 50px;
    margin-bottom: 60px;
    color: #7a7a7a;
  }
  .titulo {
    font-size: 70px;
    color: black;
  }
  .subtitulo {
    font-size: 40px;
  }
  .bajada {
    font-size: 20px;
    margin-bottom: 20px auto;
    padding: 20px; /* Espacio interno del párrafo */
    max-width: 800px; /* Ancho máximo del contenedor del párrafo */
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color:#f9f9f9;
    text-align: center; /* Centra el texto dentro del párrafo */
  }
  .titulos {
    color: #7a7a7a;
  }
  .container_2 {
     /* Contenedor para los gráficos, use flexbox para organizar los elementos */
    display: flex;
    justify-content: space-between; /* Distribuye los elementos con espacio entre ellos */
    gap: 20px; /* Espacio entre los elementos */
    height: auto; 
  }
  .item_wrapper {
    /* Contenedor para cada elemento gráfico */
    display: flex;
    flex-direction: column;
    justify-content: end; 
    align-items: left;
    flex-grow: 1;/* contenedor crece para ocupar espacio disponible */
  }
  .num_2 {
    /* años*/
    font-size: 20px;
    margin-top: 60px;
    color: #7a7a7a;
    font-family: 'Source Sans 3', sans-serif;
  }
  .circle {
    border-radius: 50%;
  }
  .cambios {
    color: #7a7a7a;
    margin: 60px auto;
    padding: 20px;
    font-size: 20px;
    text-align: center;
    max-width: 800px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color: #f9f9f9;
  }
  .flourish-container1 {
    margin-top: 100px;
    display: block; /* Muestra el contenedor como un bloque */
    margin-bottom: 40px;
  }
  .flourish-container {
    display: flex;
    gap: 20px;
    justify-content: space-evenly;  /* Distribuye los elementos con espacio igual entre ellos */
  }
  .chart-wrapper {  /* Contenedor para cada gráfico de Flourish */
    width: 50%;
    max-width: 550px;
    margin-bottom: 30px;
    margin-top: 25px;
    
  }
  .cierre {
    color: #7a7a7a;
    margin: 50px auto;
    padding: 20px;
    font-size: 20px;
    text-align: center;
    max-width: 800px;
    border: 1px solid #ddd;
    border-radius: 10px;
    background-color: #f9f9f9;
  }

  .nombre{
    color: #7a7a7a;
    margin: 30px auto;
    font-size: 15px;
    text-align: center;
  }
</style>
