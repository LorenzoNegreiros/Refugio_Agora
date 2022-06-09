<h1 align="center"> LEIA-ME </h1>
Esse é um site desenvolvido para o trabalho do segundo bimestre da matéria Desing e Desenvolvimento de Softwares para a Web.


Criei uma ONG imaginária para me inspirar.

Além dos básicos HTML5 e do CSS3, usei o JavaScript para fazer um "carousel" de imagens

<details><summary>Código usado para do Carousel</summary>

  ``` 
window.onload = function(){
    var slides = document.getElementsByClassName('carousel-item'),
        addActive = function(slide) {slide.classList.add('active')},
        removeActive = function(slide) {slide.classList.remove('active')};
    addActive(slides[0]);
    
    setInterval(function (){
      for (var i = 0; i < slides.length; i++){
        if (i + 1 == slides.length) {
          addActive(slides[0]);
          slides[0].style.zIndex = 100;
          setTimeout(removeActive, 350, slides[i]); //Doesn't be worked in IE-9
          break;
        }
        if (slides[i].classList.contains('active')) { 
          slides[i].removeAttribute('style');
          setTimeout(removeActive, 350, slides[i]); //Doesn't be worked in IE-9
          addActive(slides[i + 1]);
          break;
        }
      } 
    }, 4000);
  }
  ```
</details>
