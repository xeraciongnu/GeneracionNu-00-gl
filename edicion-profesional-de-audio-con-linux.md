---
description: 'Introdución: Latencia, Kernel RT (lowlatency) e Jack'
---

# Edición profesional de son con Linux

![](.gitbook/assets/cabeceira-alejandro_rodriguez.png)

## Edición profesional de son con Linux

### Introdución: Latencia

A pregunta que debemos facernos é se podemos abordar dunha maneira profesional a creación, edición e/ou produción de son desde Linux facendo uso, exclusivamente, de software libre.

![CC0 Creative Commons - https://pixabay.com/es/sonido-ola-forma-de-onda-aural-1781569/](.gitbook/assets/sound-1781569_640.png)

Para poder responder adecuadamente a esta cuestión, debemos empezar por considerar o \(delicado\) tema da **latencia**. Sen meternos en temas demasiado sesudos, podemos definir latencia de son como o tempo que transcorre entre o momento da emisión dun son e o momento no que se escoita. É dicir, é un retardo que se aprecia entre a xeración dun son e o son propiamente devandito.

É un tema fundamental posto que, aínda que non é posible conseguir a latencia cero -explicarémolo máis adiante-, é necesario que a latencia existente non sexa apreciable para o oído humano ou nos resultaría imposible manexar o sistema, “tocar” ou “interpretar” os sons en tempo real.

Vexamos, o son propágase a unha velocidade de 340 metros por segundo; é dicir, si emitimos un son a unha distancia dun metro, tardaremos en escoitalo algo menos de 3 milisegundos \(concretamente 2’9 milisegundos\). Baixo esta premisa, decatámonos de que calquera músico asume certa latencia implícita.

![CC0 Creative Commons - https://pixabay.com/es/guitarra-guitarra-cl%C3%A1sica-756326/](.gitbook/assets/guitar-756326_640.jpg)

Por exemplo, un guitarrista \(acústico\) ten a fonte de son a uns 40 cm polo que tardará preto de 1 milisegundo en escoitalo. Un violinista \(está a uns 10 cm da súa fonte de son\) uns 0’3 milisegundos. Un guitarrista eléctrico, si atópase a uns 3 metros do amplificador, terá que soportar unha latencia de 9 milisegundos.  
Este exemplo pódese facer aínda máis complexo se pensamos nun grupo de varios instrumentistas tocando en distintas partes dun escenario e tentando tocar todos xuntos e compasados. Pero ese non é o tema que nos ocupa polo que o deixaremos para mellor ocasión.

Un computador, como xa dixemos, tamén ten latencia pero, neste caso, non se debe á distancia entre o emisor e o receptor si non entre a xeración do son e a emisión efectiva do mesmo. Igualmente, que no caso anterior, hai certos límites de latencia admisibles \(por ser imperceptibles polo oído humano\).  
**Polo xeral podemos admitir, para un sistema “en tempo real”, unha latencia de 11 milisegundos.**

### Kernel RT \(lowlatency\)

Como abordamos, pois, o tema da latencia de son dun computador que funcione baixo o Sistema Operativo GNU/Linux? A resposta é sinxela: utilizando un Kernel RT \(lowlatency ou de baixa latencia\). O Kernel “normal” de Linux é multitarea e ten un sistema de control de prioridades pero non podemos interromper os procesos en “calquera sitio” e é onde aparece a latencia. Un Kernel RT controla a prioridade dos procesos e é capaz de xestionar dunha maneira máis eficiente esa latencia.

![CC0 Creative Commons - https://pixabay.com/es/plato-giratorio-vista-superior-1337986/](.gitbook/assets/turntable-1337986_640.jpg)

Tamén podemos contribuír a diminuíla utilizando hardware máis moderno e potente. De feito, para un uso non intensivo do procesamento de sinal de son non é necesario dispor dun kernel de baixa latencia, simplemente chegará cun hardware adecuado.  
Un exemplo sería o procesado de son con Audacity: podemos gravar ou editar son sen necesidade de ter instalado un kernel de baixa latencia.

Si quixésemos instalar un Kernel RT en GNU/Linux \(por exemplo nunha distro da rama Debian\) debiéramos facelo da seguinte maneira:

```text
 sudo apt-get install linux-headers-lowlatency sudo apt-get install linux-lowlatency sudo update-grub
```

### Jack

Unha vez instalado o Kernet RT, para poder xestionar as conexións de audio entrantes e saíntes no noso sistema operativo Linux, usaremos JACK \(Jack Audio Conection Kit, [http://jackaudio.org/](http://jackaudio.org/)\) que é un servidor de son que prové de conexións de baixa latencia entre aplicacións.

Esta é a pantalla principal de QjackCt \([https://qjackctl.sourceforge.io/](https://qjackctl.sourceforge.io/) unha interface gráfica de jack que nos axuda á hora de interactuar co programa\)

![Fonte das imaxes: https://qjackctl.sourceforge.io/qjackctl-screenshots.html](.gitbook/assets/image%20%284%29.png)

E esta é a xanela de configuración onde podemos observar \(abaixo á dereita\) que con esa configuración conséguese unha latencia de 5’8 milisegundos \(calquera valor por baixo de 11 milisegundos é máis que aceptable\).

![](.gitbook/assets/image%20%2814%29.png)

Unha vez configurado JACK \(cousa da que nos ocuparemos noutro momento\) estamos en disposición de empezar a traballar co noso software de son \(composición, edición, produción, …\) na nosa distribución de GNU/Linux favorita. De feito, existen distribucións específicas de Linux para o tratamento de son a todos os niveis \(Ubuntu Studio, KXStudio, Musix, AVLinux, ...\).  
Tanto a configuración do servidor de audio JACK, como a elección do software que queremos usar e/ou a distribución máis adecuada son temas que trataremos máis adiante.

**Até logo e que non pare a música!**



### [Seguinte artigo](debuxos-libres.md)

