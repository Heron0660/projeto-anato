<!DOCTYPE html>
<html>
<head>
  <title>Apresentação com Temporizador</title>
</head>
<body>
  <h1>Tela de Apresentação</h1>
  <div id="presentation"></div>
  <input type="text" id="answer" placeholder="Insira sua resposta">
  <button onclick="nextSlide()">Próxima Tela</button>

  <script>
    const presentation = document.getElementById('presentation');
    const answerInput = document.getElementById('answer');
    const slides = [
      'Tela 1: Conteúdo da Tela 1',
      'Tela 2: Conteúdo da Tela 2',
      'Tela 3: Conteúdo da Tela 3',
      'Tela 4: Conteúdo da Tela 4',
      'Tela 5: Conteúdo da Tela 5',
      'Tela 6: Conteúdo da Tela 6',
      'Tela 7: Conteúdo da Tela 7',
      'Tela 8: Conteúdo da Tela 8',
      'Tela 9: Conteúdo da Tela 9',
      'Tela 10: Conteúdo da Tela 10'
    ];

    let currentSlide = 0;
    let timer;

    function displaySlide(slideIndex) {
      presentation.innerHTML = slides[slideIndex];
      answerInput.value = ''; // Limpa a resposta anterior
      startTimer();
    }

    function startTimer() {
      clearInterval(timer);
      let timeLeft = 60; // 60 segundos
      timer = setInterval(function() {
        timeLeft--;
        if (timeLeft === 0) {
          nextSlide();
        }
      }, 1000);
    }

    function nextSlide() {
      if (currentSlide < slides.length - 1) {
        currentSlide++;
        displaySlide(currentSlide);
      }
    }

    displaySlide(currentSlide);
  </script>
</body>
</html>
