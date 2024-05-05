# Configuración de visual studio code para compilar STM32 con CMake

### 1) Para Mostrar los presets disponibles. ejecutar en la linea de comandos:
``` 
cmake --list-presets
 ```
Salida:
``` 
Available configure presets:

  "Debug"
  "RelWithDebInfo"
  "Release"
  "MinSizeRel"
```
### 2) Para configurar el preset para generar el Debug
```
cmake . --preset Debug
```
### 3) Para construir los ejecutables (elf,bin,hex)
```
cmake --build build\Debug
```
### 4) Para generar (.hex) agregar en el CMakeList.txt del raiz.
```
	add_custom_command(
	    TARGET ${CMAKE_PROJECT_NAME} POST_BUILD
	    COMMAND ${CMAKE_OBJCOPY} -O ihex $<TARGET_FILE:${CMAKE_PROJECT_NAME}> ${CMAKE_PROJECT_NAME}.hex
	)
```
### 5) Para generar (.bin) agregar en el CMakeList.txt del raiz.
```
	add_custom_command(
	    TARGET ${CMAKE_PROJECT_NAME} POST_BUILD
	    COMMAND ${CMAKE_OBJCOPY} -O binary $<TARGET_FILE:${CMAKE_PROJECT_NAME}> ${CMAKE_PROJECT_NAME}.bin
	)
```
### 6) Para incluir funcion printf modificar el archivo (gcc-arm-none-eabi.cmake) del directorio cmake.
```
	set(CMAKE_C_LINK_FLAGS "${CMAKE_C_LINK_FLAGS} --specs=nosys.specs")
```

