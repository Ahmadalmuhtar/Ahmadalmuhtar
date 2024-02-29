<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Animation</title>
  <style>
    #animatedElement {
      width: 100px;
      height: 100px;
      background-color: blue;
      position: absolute;
    }
  </style>
</head>
<body>
  <div id="animatedElement"></div>

  <script>
    // Get the animated element
    const animatedElement = document.getElementById('animatedElement');
    
    // Set initial position and speed
    let positionX = 0;
    let speed = 2;

    // Define the animate function
    function animate() {
      // Update position
      positionX += speed;

      // Apply new position
      animatedElement.style.left = positionX + 'px';

      // Check boundary and reverse direction if needed
      if (positionX <= 0 || positionX >= window.innerWidth - animatedElement.clientWidth) {
        speed = -speed;
      }

      // Repeat animation
      requestAnimationFrame(animate);
    }

    // Start animation
    animate();
  </script>
</body>
</html>
