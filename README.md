# POO-SistemaReservaTurno
## Clases ADMIN
Creamos
  - Panel de menu de admin 
  - Panel Turnos
  - Panel Pacientes
  - Panel Odontologos
  - Panel Nuevo odontologo
  - Agregamos pop-ups de informacion
  
Modificamos/Agreamos
  - PanelAdmin en el PanelManager
  - Considerar Log in de admin en la funcion iniciarSesion del PanelLogin

## Clase negocio Paciente
Sacamos
  - Pagar turno (del codigo y UML)
  - cancelarTurno (del codigo y UML)
  - modificarTurno (del codigo y UML)
  - Sacar turno (del codigo y UML)
  - iniciarSesion (del codigo y UML)
  - List turnos (del codigo)

Modificamos
  - Fecha alta: lo pasamos a string (cambiamos el codigo y uml)

## Clase negocio Odontologo
Sacamos
  - List turnos (del codigo)

## Clase TurnoDAO
Modificamos
  - guardar: encontramos una forma de ahorrar un For aprovechando la porpiedad de que un turno nuevo tendra un Codigo=0. Simplifica mucho el metodo

## Clase Usuario
Sacamos
  - La clase entera
	- El archivo usuarios.txt
  
## Clase PanelFormulario
Sacamos
  - La clase entera. Era un borrador redundante con PanelNuevoTurno

## Panel Nuevo turno
Agregamos
  - Popup de informacion

## Panel turnos
Agregamos
  - Popup de informacion

## PanelRegistrar
Agregamos
  - Clase entera

## PanelManager
Agregamos
  - Método armarPanelRegistrar()
  - Método mostrarPanelRegistrar()

## Ejecutables
Modificamos
  - El package name paso de "test" a "Ejecutables"

Agregamos
  - Un ejecutable ("Batch de Prueba") que crea un set de pacientes/odontologos/turnos para hacer pruebas

## Paneles en general
Modificamos
  - Tamaños y colores para que quede todo más visual y que haya consistencia entre las distintas pantallas.

# Known issues
### Ver con el profe
- [ ] UML: Relacion de 1 a muchos en el UML entre Paciente y Turno (Dado que la clase Paciente no tiene mas atributo Lista Turnos)
- [ ] UML: Relacion de 1 a muchos en el UML entre Odontologo y Turno (Dado que la clase Odontologo no tiene mas atributo Lista Turnos)
- [ ] PanelManager: Variables globales: es un archivo de manejo de paneles, queda medio fruta la variable global. Hay que ver si necesita remediacion (podriamos consultarlo con Javi)
### Otros
- [ ] PacienteDAO: recuperar: Hay que tener en cuenta para el resto del codigo que puede devolver un null.	
- [ ] OdontologoDAO: recuperar: Hay que tener en cuenta para el resto del codigo que puede devolver un null.
- [ ] TurnoDAO: recuperar: Hay que tener en cuenta para el resto del codigo que puede devolver un null.
		
### Resolved
- [x] PacienteDAO: linea 19. No sabemos si funciona bien .remove con objeto. Tomar como ejemplo funcion linea 28
- [x] OdontologoDAO: linea 21. No sabemos si funciona bien .remove con objeto. (Mismo problema que PacienteDAO)
- [x] ServiceTurno/TurnoDAO: guardar: Mover la excepcion a la logica de negocio (Service). (Ver de actualizarlo en la interfaz)
- [x] PanelManager: preguntar que hace setLocationRelativeTo.
- [x] Boton modificar turno: Si no hay un turno seleccionado, loguea errores en la consola (Arreglar con un popup)
- [x] PanelNuevoTurno: linea 70: que es el Jmenu
- [x] PanelNuevoTurno: ver si hacemos panel ModificarTurno separado de nuevo turno
- [x] TurnoDAO: guardar: sacar el For de la Excepcion a consenso de Tino
- [x] ServiceTurno: Hacer la excepcion Turno ya existente
- [x] Estructura clases de negocio: En cada Turno guardamos todo el objeto Paciente y Odontologo. Estos ya los tenemos guardados en sus respectivos archivos. Estmaos guardadno lo mismo duplicado
- [x] ServicePaciente: setPacienteDAO no se usa y no tiene mucho sentido en lo que tenemos. (Por ejemplo, en ServiceOdontologo no esta)
- [x] BatchDePrueba: No reconoce el serviceTurno.
	
