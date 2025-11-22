1. Cargar la imagen:
JavaScriptlet src = cv.imread('imageCanvasInput');
let dst = src.clone();
2. Gris + desenfoque suave (elimina ruido):
cv.cvtColor(src, gray, cv.COLOR_RGBA2GRAY);
cv.GaussianBlur(gray, blurred, new cv.Size(5,5), 0);
3. Canny bien calibrado (esto es clave para contornos limpios)JavaScriptcv.Canny(blurred, edges, 75, 200);  
4. Crear contornos (¡¡la línea que siempre fallaba!!)JavaScriptlet contours = new cv.MatVector();  
let hierarchy = new cv.Mat();
cv.findContours(edges, contours, hierarchy, cv.RETR_EXTERNAL, cv.CHAIN_APPROX_SIMPLE);
5. Dibujar en verde neón gruesoJavaScriptlet neon = new cv.Scalar(0, 255, 150, 255);  // o 0,255,100 para más brillo
cv.drawContours(dst, contours, -1, neon, 4); // -1 = todos los contornos, grosor 4
6. Mostrar y limpiar memoria (obligatorio en el navegador)JavaScriptcv.imshow('outputCanvas', dst);

