# Modulo Programador -  ABP

### Automatización del Hogar

1. Luces inteligentes ( encender, apagar, cambiar intensidad o color )
2. Aire / Calefacción ( encender, ajustar temperatura )
3. Puertas inteligentes ( abrir / cerrar, bloquear / desbloquear )
4. Sistema de riego automático ( activar, programar días y horarios )

### Introducción

La automatización es el uso de tecnología para controlar y gestionar automáticamente distintos dispositivos y sistemas del hogar: luces, climatización, seguridad, etc

La automatización de puertas inteligentes es una solución tecnológica que permite, el control de acceso a una determinada puerta de forma automática

---

### Requerimientos funcionales del programa

- **Gestión de dispositivos**
    
    El programa debe permitir registrar dispositivos nuevos y estado inicial, con posibilidad de poder modificar las caracteristicas del dispositivo
    
- **Control de Estado**
    
    El usuario puede ver el estado actual de todos los dispositivos registrados
    
- **Automatización**
    
    Implementar reglas automáticas como el bloqueo / desbloqueo  automático de puertas
    
- **Transparencia Algorítmica**
    
    El sistema contiene la documentación correspondiente de forma clara y concisa sobre como funcionan las automátizaciones
    

### Problemáticas extra para elegir (Automatización)

> “ Se puede establecer una alarma, en donde se notifique al usuario el estado de las puertas, como metodo de recordatorio de seguridad  “ 12pm - “ Todas las puertas están bloqueadas ”
> 

---

## Primera Instancia ( aproximación con JSON )

### Gestionar los dispositivos

- Listar

```python

```

- Buscar
- Agregar

```python
def agregar_puerta(puertas, nombre):
    mensaje_error = validar_inputs(nombre)
    if mensaje_error:
        print(mensaje_error)
        return

    for puerta in puertas:
        if puerta["nombre"].lower() == nombre.lower():
            print("La puerta ingresada ya esta registrada.")
            return

    puertas.append(nueva_puerta(nombre))
    guardar_puertas(puertas)
    print("La puerta fue agregada exitosamente.")
```

- Eliminar

### Gestionar automatizaciones ( primera instancia )

- Utilizaremos JSON como herramienta para la gestión momentanea de configuraciones y acceso, listar dispositivos, buscar dispositivos, agregar dispositos o eliminar dispositivos
- JSON ofrece simplicidad, legibilidad y compatibilidad. Nos permite trabajar la información en estructuras de datos, facilitando el trabajo con datos estructurados, facilmente integrable en sistemas de automatización como el sistema de puertas inteligentes
- Se realizará un menú por consola, donde pérmitiremos al usuario realizar acciones tales como, agregar, listar, buscar o eliminar dispositivos
