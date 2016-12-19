@author Santiago Maraggi

DEMO API: "Microsoft Media Foundation"

Microsoft Media Foundation (MMF) es la API nueva de Microsoft para manipulaci�n de archivos multimedia en distintos formatos y para su reproducci�n en distintos medios disponibles en la familia de sistemas operativos Microsoft Windows �nicamente.

MMF viene integrado con el WindowsSDK, que incorpor� funcionalidades de Microsoft Windows antes dispersas en otras APIs, como DXSDK.

MMF reemplaza antiguos ActiveX Controls y funcionalidades de Windows Media Player que se pod�an llamar desde programas para favorecer la protecci�n de contenido con licencias y derechos de autor, principalmente, a pesar de ofrecer tambi�n algunas facilidades para flexibilizar m�s la manipulaci�n de los distintos streams multimedia.

El presente proyecto implementa un sencillo reproductor de video utilizando los servicios de MMF.

Los servicios ofrecidos por MMF son de bajo nivel, a tal punto que el reproductor manipula los buffers de audio y video por separado, puede acceder a su sincronizaci�n y a la configuraci�n de un pipeline de reproducci�n con hardware espec�fico, que en este caso se deja referenciado al monitor y reproductor de audio por defecto.

Para su desarrollo se consult� la documentaci�n on line de Microsoft y se tomaron partes de c�digo de ejemplo publicadas, siendo necesarias algunas adaptaciones para componer el reproductor completo y responder a algunas necesidades previsibles para aplicaciones que deban manipular y reproducir videos.

Instrucciones de uso
********************

Ejecutar el programa

Al iniciarse el programa se inicializa tambi�n el m�dulo de video (CPlayer).

En el men� seleccionar la opci�n "Cargar Video". Esto cargar� el video por defecto configurado en la aplicaci�n. Para dar comienzo y pausar la reproducci�n se utiliza la barra espaciadora una vez cargado el video.

Utilizar teclas "q" y "w" para saltear a partes predefinidas del video. Aqu� se implementa un "pause"-"seek"-"play".

El programa se debe ejecutar desde Visual Studio 2010 debido a que los dos archivos de video est�n en el directorio del proyecto. Para ejecutar el programa por fuera del Visual Studio se debe copiar los dos archivos de video al directorio de ejecuci�n del programa.

A continuaci�n se detallan todas las teclas y sus respectivos comandos que se pueden utilizar.

Se puede cerrar la aplicaci�n en cualquier momento, pasar al video alternativo y nuevamente al original con la tecla ENTER y ejecutar en general estos comandos en cualquier orden.

Esta lista de comandos se encuentra tambi�n documentada en el archivo "MediaFoundationPlayer.cpp". Los comandos se ejecutan con la tecla directamente en min�scula.
// **************************************************************************
// **************************************************************************
// **************************************************************************
// *********** DEMO VIDEO PLAYER CON MICROSOFT MEDIA FOUNDATION *************

// Ejecutar la aplicaci�n y seleccionar del men� principal "Reproducir Video"

// Uso general:
// En el men� superior elegir la opci�n "Cargar video"
// Luego iniciar la reproducci�n con la barra espaciadora
// Utilizar el resto de los controles...
// Cerrar la aplicaci�n al terminar

// Mapa de teclas de control de reproducci�n

// ESPACIO - Play / Pausa
// Q - Salto hacia atr�s 5 segundos
// W - Salto hacia adelante 5 segundos
// E - Volumen de audio m�ximo 1.0
// R - Volumen de audio 0.5
// T - Volumen de audio nulo 0.0 (mute)
// A - Velocidad de reproducci�n x1.0 (normal)
// S - Velocidad de reproducci�n x2.0 (r�pido)
// D - Velocidad de reproducci�n x0.5 (lento)
// Z - Velocidad de reproducci�n x4.0 (muy r�pido)
// X - Deprecated
// ENTER - Cambiar de video

// **************************************************************************
// **************************************************************************
// **************************************************************************

Al salir del programa se cierra el m�dulo de video (CPLayer). Si el video estaba en reproducci�n se lo detiene previamente para proceder a cerrar el m�dulo de video correctamente.

Referencias
***********

https://msdn.microsoft.com/en-us/library/windows/desktop/ms703190(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/ms703190(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979592(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979593(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979594(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979595(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979596(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979597(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd979598(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/ff728866(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/ms697048(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/ee892373(v=vs.85).aspx
https://msdn.microsoft.com/en-us/library/windows/desktop/dd389281(v=vs.85).aspx#getting_file_duration
https://msdn.microsoft.com/en-us/library/windows/desktop/ms703153(v=vs.85).aspx
http://stackoverflow.com/questions/19211610/how-can-i-read-the-info-of-a-media-file-using-visual-c
https://msdn.microsoft.com/en-us/library/windows/desktop/bb762197(v=vs.85).aspx
https://social.msdn.microsoft.com/Forums/windowsdesktop/en-US/41b62ea7-dd6c-4963-b251-280d2f075c71/is-it-possible-to-get-the-number-of-video-frames-for-a-file-using-the-source-reader?forum=mediafoundationdevelopment
