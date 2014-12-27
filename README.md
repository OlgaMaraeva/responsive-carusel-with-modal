responsive-carusel-with-modal
=============================

Responsive carusel with modal slide show. This script share just a basic design. If you need extra styles you can grab it from here:
http://luckyframe74.com/demo/carusel/index.html

Чтобы прокручивать карусель колесиком мыши, сделайте следующее.

1. Удалите кнопки прокрутки в index.html:

  <div class="btnLeft"></div><!--end btnLeft-->
  <div class="btnRight"></div><!--end btnRight-->
  
2. В файле carusel.js замените кусок кода

// Prev and next button for carusel
 
    $('div.btnLeft').click(function () {
        moveLeft();
    });
 
    $('div.btnRight').click(function () {
        moveRight();
    });
    
на

  $('#slider ul').on( 'DOMMouseScroll mousewheel', function ( event ) {
  if( event.originalEvent.detail > 0 || event.originalEvent.wheelDelta < 0 ) { //alternative options for wheelData: wheelDeltaX & wheelDeltaY
    //scroll down
    moveLeft();
  } else {
    //scroll up
    moveRight();
  }
  //prevent page fom scrolling
  return false;
});

