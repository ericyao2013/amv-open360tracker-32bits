# Sistema de Control de Servo PAN sin PIDS

Se ha inclu�do de forma experimental un sistema de control del servo PAN que no usa PID. Si usas un servo lento, este sistema podr�a mejorar el seguimiento del tracker, realizando movimientos m�s precisos y flu�dos. El sistema es m�s intiutivo de configurar que el sistema PID tradicional.
El sistema realiza una correcci�n de forma proporcional del �ngulo de error entre el heading del tracker y el heading del aeromodelo, mapeando dicho error sobre un rango de pulsos PWM para el servo en base a los siguientes par�metros:

- **NO_PID_CONTROL:** Descomentando este par�metro desactivamos el sistema PID tracicional y activamos el nuevo sistema de control PAN.
- **MIN_DELTA:** Angulo m�nimo en grados entre el heading del tracker y el del aeromodelo, si es mayor que este �ngulo movemos el tracker.
- **MIN_PAN_SPEED:** Cantidad m�nima en milisegundos que hay que incrementar el pulso del PAN_0 para que se mueva. Este par�metro es com�n a ambos sistemas de control y est� localizado en el config.h donde siempre ha estado.
- **MAX_PAN_SPEED:** Cantidad m�xima en milisegundos que hay que incrementar el pulso del PAN_0 para que se mueva.
- **MAP_ANGLE:** �ngulo en grados a partir del cual se empieza a mapear el error del �ngulo al gradiente de pulsos.