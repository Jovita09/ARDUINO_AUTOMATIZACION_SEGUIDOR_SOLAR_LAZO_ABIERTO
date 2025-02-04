# ARDUINO_AUTOMATIZACION_SEGUIDOR_SOLAR_LAZO_ABIERTO
Este código para ESP32 controla un actuador lineal mediante un puente H, utilizando un potenciómetro para la extensión/contracción y otro para medir el ángulo. Además, envía los valores de ángulo y velocidad por serial para su monitoreo en tiempo real.

Inicialización:

Se configuran los pines de entrada (potenciómetros) y salida (puente H y PWM).
Se inicializa la comunicación serial a 115200 baudios.
Lectura de sensores:

Se leen los valores de los potenciómetros:
potPin (26): Control del actuador.
potPinA (25): Medición del ángulo.
Se convierte el valor del potenciómetro A en ángulo mediante una regla de tres.
Control del actuador:

Si el potenciómetro de control (potValue) es mayor a 2047, el actuador se extiende.
Si es menor a 1024, el actuador se contrae.
Si está en el rango medio, el actuador se detiene.
Se usa PWM en enablePin (14) para regular la velocidad del actuador.
Cálculo de velocidad:

Se calcula vf, una versión escalada del valor de PWM, con vf = v / 21.
Envío de datos por serial:

Se imprime por puerto serial el ángulo y la velocidad (vf).
Se puede visualizar en MATLAB o cualquier software de monitoreo serial.
