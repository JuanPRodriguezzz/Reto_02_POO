# Reto_02_POO
### Juan Pablo Rodríguez 

1. Elija un problema de la vida real (sistema de gestión de biblioteca, negocio de compra-venta, automóvil, etc) que se pueda modelar a través de objetos y clases. Plantee las relaciones de clases, composiciones, propiedades y comportamientos del sistema en uno mas diagramas tipo UML.


´´´Mermaid

classDiagram
    class SistemaReservaciones {
        + List~RecursoReservable~ recursos
        + List~Usuario~ usuarios
        + List~Reservacion~ reservaciones
        + agregarRecurso(recurso: RecursoReservable): void
        + registrarUsuario(usuario: Usuario): void
        + generarReservacion(reservacion: Reservacion): void
    }

    class Usuario {
        + String nombre
        + String identificación
        + List~Reservacion~ reservaciones
        + consultarReservaciones(): void
        + cancelarReservacion(reservacion: Reservacion): void
    }

    class RecursoReservable {
        + String nombre
        + String tipo
        + String disponibilidad
        + consultarDisponibilidad(fechaInicio: Date, fechaFin: Date): Boolean
        + actualizarDisponibilidad(estado: String): void
    }

    class Reservacion {
        + Usuario usuario
        + RecursoReservable recurso
        + Date fechaInicio
        + Date fechaFin
        + cancelarReservacion(): void
    }

    SistemaReservaciones --> "1..*" Usuario
    SistemaReservaciones --> "1..*" RecursoReservable
    SistemaReservaciones --> "1..*" Reservacion
    Reservacion --> "1" Usuario
    Reservacion --> "1" RecursoReservable

´´´
