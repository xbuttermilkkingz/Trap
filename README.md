# Bookmark FPS! WORKS 2025
javascript:(function(){
    // Create a new div element to display the FPS
    var fpsDiv = document.createElement('div');
    fpsDiv.style.position = 'fixed';
    fpsDiv.style.top = '10px';
    fpsDiv.style.right = '10px';
    fpsDiv.style.padding = '5px 10px';
    fpsDiv.style.backgroundColor = 'rgba(0, 0, 0, 0.7)';
    fpsDiv.style.color = '#fff';
    fpsDiv.style.fontSize = '16px';
    fpsDiv.style.zIndex = '9999';
    document.body.appendChild(fpsDiv);

    // Variables to calculate FPS
    var lastFrameTime = 0;
    var frameCount = 0;
    var fps = 0;

    // Function to update the FPS counter
    function updateFPS() {
        var currentFrameTime = performance.now();
        frameCount++;
        if (currentFrameTime - lastFrameTime >= 1000) {
            fps = frameCount;
            frameCount = 0;
            lastFrameTime = currentFrameTime;
            fpsDiv.textContent = fps + ' FPS';
        }
        requestAnimationFrame(updateFPS);
    }

    // Start the FPS counter
    updateFPS();
})();
