# js-demo-1
1. This is a draggable div element, made by orginal javascript.
2. Once you clicked the div,you can make it move by dragging your mouse.
3. the core code is below.
 ```javascript
  var Div = document.createElement('div');

  Div.className='demo';

  document.body.appendChild(Div);

  var dragging = false;

  var lastX;

  var lastY;

  Div.onmousedown = function (e) {
      console.log('原始位置');
      lastX=e.clientX;
      lastY=e.clientY;
      dragging=true;
  }
  document.onmousemove = function (e) {

      if(dragging===true){

          var deltaX=e.clientX -lastX;

          var deltaY=e.clientY -lastY;

          var top = parseInt(Div.style.top) || 0;

          var left = parseInt(Div.style.left) || 0;

          var resultX = top + deltaY;

          var resultY = left + deltaX;

          if(resultX<0){
              resultX=0;
          }
          if(resultY<0){

              resultY=0;
          }

          Div.style.top = resultX + 'px';

          Div.style.left = resultY + 'px';

          lastX = e.clientX;

          lastY = e.clientY;

          console.log('Div style top');

          console.log(Div.style.top);


      }
  }

  document.onmouseup=function (ev) {
      dragging=false;
  }
 ```
