# chinchina-psicologia
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Salud Mental / Mental Health en Chinchiná</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
  body { font-family: Arial, sans-serif; margin: 20px; background: #f0f4f8; color: #333; }
  .container { max-width: 700px; margin: auto; background: white; padding: 20px; border-radius: 10px; box-shadow: 0 3px 10px rgba(0,0,0,0.1); }
  h1, h2 { color: #2c3e50; }
  p, li { font-size: 16px; line-height: 1.5; }
  ul { padding-left: 20px; }
  button { margin-bottom: 20px; padding: 10px 15px; font-size: 16px; cursor: pointer; background: #2980b9; border: none; color: white; border-radius: 5px; }
  button:hover { background: #1c5980; }
  .hidden { display: none; }
  a { color: #2980b9; text-decoration: none; }
  a:hover { text-decoration: underline; }
</style>
</head>
<body>

<div class="container">
  <button id="toggleLangBtn">English</button>

  <div id="es">
    <h1>Mejora de la salud mental en Chinchiná, Caldas</h1>
    <canvas id="chartES" width="600" height="400"></canvas>

    <h2>Dónde buscar ayuda</h2>
    <p>En Chinchiná, puedes ir al <strong>Hospital San Marcos</strong> o ver a psicólogos que ayudan con problemas de mente y emociones.</p>
    <ul>
      <li>Maira Alejandra Castro - Terapia para sentir mejor</li>
      <li>Valentina López - Ayuda para controlar emociones</li>
      <li>Brenda Ocampo - Psicóloga profesional</li>
      <li>Hospital San Marcos - Servicios de psicología y psiquiatría</li>
    </ul>

    <h2>Datos importantes</h2>
    <p>En los últimos años, más personas en Chinchiná participan en actividades para mejorar su salud mental. En 2023, un 35% más que en 2019.</p>
  </div>

  <div id="en" class="hidden">
    <h1>Mental Health Improvement in Chinchiná, Caldas</h1>
    <canvas id="chartEN" width="600" height="400"></canvas>

    <h2>Where to get help</h2>
    <p>In Chinchiná, you can go to <strong>Hospital San Marcos</strong> or see psychologists who help with mind and emotions problems.</p>
    <ul>
      <li>Maira Alejandra Castro - Therapy to feel better</li>
      <li>Valentina López - Help to control emotions</li>
      <li>Brenda Ocampo - Professional psychologist</li>
      <li>Hospital San Marcos - Psychology and psychiatry services</li>
    </ul>

    <h2>Important data</h2>
    <p>In recent years, more people in Chinchiná join activities to improve mental health. In 2023, 35% more than in 2019.</p>
  </div>
</div>

<script>
  // Datos para la gráfica
  const dataES = {
    labels: ['2019', '2020', '2021', '2022', '2023'],
    datasets: [{
      label: 'Participación en actividades (%)',
      data: [20, 25, 28, 32, 35],
      backgroundColor: 'rgba(41, 128, 185, 0.7)',
      borderColor: 'rgba(41, 128, 185, 1)',
      borderWidth: 1
    }]
  };

  const dataEN = {
    labels: ['2019', '2020', '2021', '2022', '2023'],
    datasets: [{
      label: 'Participation in activities (%)',
      data: [20, 25, 28, 32, 35],
      backgroundColor: 'rgba(41, 128, 185, 0.7)',
      borderColor: 'rgba(41, 128, 185, 1)',
      borderWidth: 1
    }]
  };

  const options = {
    responsive: true,
    scales: {
      y: {
        beginAtZero: true,
        max: 40,
        title: {
          display: true,
          text: 'Porcentaje (%) / Percentage (%)'
        }
      },
      x: {
        title: {
          display: true,
          text: 'Año / Year'
        }
      }
    },
    plugins: {
      legend: { display: true, position: 'top' },
      title: {
        display: true,
        text: 'Mejora en la participación en salud mental / Improvement in mental health participation'
      }
    }
  };

  // Crear gráficos
  const ctxES = document.getElementById('chartES').getContext('2d');
  const chartES = new Chart(ctxES, {
    type: 'bar',
    data: dataES,
    options: options
  });

  const ctxEN = document.getElementById('chartEN').getContext('2d');
  const chartEN = new Chart(ctxEN, {
    type: 'bar',
    data: dataEN,
    options: options
  });

  // Cambiar idioma
  const btn = document.getElementById('toggleLangBtn');
  const esDiv = document.getElementById('es');
  const enDiv = document.getElementById('en');

  btn.addEventListener('click', () => {
    if (esDiv.classList.contains('hidden')) {
      esDiv.classList.remove('hidden');
      enDiv.classList.add('hidden');
      btn.textContent = 'English';
    } else {
      esDiv.classList.add('hidden');
      enDiv.classList.remove('hidden');
      btn.textContent = 'Español';
    }
  });
</script>

</body>
</html>
