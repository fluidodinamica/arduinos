# Arduinos

### Arduino y Ubuntu

En julio de 2022, un bug impide la detección directa de las placas.
  0. Instalar Arduino desde la versión 64bits del ditio wev (no usar apt install)

  1. Aplicación Arduino:  error java.lang.UnsatisfiedLinkError: /usr/lib/x86_64-linux-gnu/liblistSerialsj
  
     Se resuelve siguiendo los pasos indicados en https://bugs.launchpad.net/ubuntu/+source/arduino/+bug/1916278
     
     ```     
     sudo apt install libserialport0 patchelf
     
     sudo patchelf --add-needed /usr/lib/x86_64-linux-gnu/libserialport.so.0 /usr/lib/x86_64-linux-gnu/liblistSerialsj.so.1.4.0
     ```
  2. Placa no detectada. Según  https://askubuntu.com/questions/1408192/can-not-connect-arduino-ide-with-arduino-board-on-ubuntu-22-04
    ```
    sudo apt remove brltty
    ```
    
     y reiniciar resuelve el conflicto.
     
  3. Un horrible bug no permitía detectar librerías instaladas. Para ello:  
    ```
    sudo apt install  avr-libc gcc-avr 
    ```   
    
### Win 11
  1. Parece que habría un conflicto con Windows pero eso lo dejo investigar y editar para quienes usen ese SO.
