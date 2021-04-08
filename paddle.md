  <script>
    var canvas = document.querySelector("#myCanvas");
    var context = canvas.getContext("2d");

    window.addEventListener("keydown", moveSomething, false);
  
    var deltaX = 0;
    var deltaY = 0;
 
function moveSomething(e) {
    switch(e.keyCode) {
        case 37:
            deltaX  = Math.max(deltaX-20, -170);
            break;
        // case 38:
        //     deltaY -= 2;
        //     break;
        case 39:
            deltaX = Math.min(deltaX+20, canvas.width-230);
            break;
        // case 40:
        //     deltaY += 2;
        //     break;
    }
    e.preventDefault();
    drawPaddle()
}    
    
function drawPaddle() {
  context.clearRect(0, 0, canvas.width, canvas.height);
  // the paddle
  context.beginPath();
  context.lineTo(170 + deltaX, 325 + deltaY);
  context.lineTo(230 + deltaX, 325 + deltaY);
  context.closePath();
 
  // the outline
  context.lineWidth = 10;
  context.strokeStyle = "rgba(102, 102, 102, 1)";
  context.stroke();
 
}
drawPaddle();
  </script>
