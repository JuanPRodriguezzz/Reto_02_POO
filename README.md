# Reto_02_POO
### Juan Pablo Rodríguez 

1. Elija un problema de la vida real (sistema de gestión de biblioteca, negocio de compra-venta, automóvil, etc) que se pueda modelar a través de objetos y clases. Plantee las relaciones de clases, composiciones, propiedades y comportamientos del sistema en uno mas diagramas tipo UML.

# Sistema de reservaciones
```mermaid

classDiagram
    class SistemaReservaciones {
        + List recursos
        + List usuarios
        + List reservaciones
        + agregarRecurso()
        + registrarUsuario()
        + generarReservacion()
    }

    class Usuario {
        + String nombre
        + String identificación
        + List reservaciones
        + consultarReservaciones()
        + cancelarReservacion()
    }

    class RecursoReservable {
        + String nombre
        + String tipo
        + String disponibilidad
        + consultarDisponibilidad(fechaInicio: Date, fechaFin: Date)
        + actualizarDisponibilidad()
    }

    class Reservacion {
        + Usuario usuario
        + RecursoReservable recurso
        + Date fechaInicio
        + Date fechaFin
        + cancelarReservacion()
    }

    SistemaReservaciones *-- "1..*" Usuario
    SistemaReservaciones *-- "1..*" RecursoReservable
    SistemaReservaciones *-- "1..*" Reservacion
    Reservacion --|> "1" RecursoReservable
    

```
