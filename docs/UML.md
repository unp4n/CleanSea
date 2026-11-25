```mermaid
    usecase-beta
    direction LR
    actor Jugador
    actor Sistema

    systemBoundary recoleccion["Recolección"]
        Herramienta("Seleccionar herramienta o equipo")
        Recolectar("Recolectar basura")
        Clasificar("Clasificar basura")
        Inventario("Ver inventario")
        Descartar("Descartar basura sin valor")
    end

    systemBoundary economia["Economía"]
        Vender("Vender basura")
        Precios("Consultar precios de la basura")
        Comprar("Comprar mejoras")
        Catalogo("Ver catálogo de la tienda")
        Dinero("Consultar dinero")
    end

    systemBoundary progresion["Progresión y niveles"]
        Progreso("Ver porcentaje de limpieza")
        Avanzar("Avanzar de nivel")
        Verificar("Verificar porcentaje requerido")
        Regresar("Regresar a un nivel anterior")
        Seleccionar("Seleccionar nivel")
        Estadisticas("Ver estadísticas del cuerpo de agua")
    end

    systemBoundary partida["Sistema y partida"]
        Guardar("Guardar partida")
        Cargar("Cargar partida")
        Nuevo("Iniciar nuevo juego")
        Opciones("Configurar opciones (sonido, controles)")
        Tutorial("Ver tutorial")
    end

    Jugador -- Herramienta
    Jugador -- Recolectar
    Jugador -- Inventario
    Jugador -- Descartar
    Jugador -- Vender
    Jugador -- Precios
    Jugador -- Comprar
    Jugador -- Dinero
    Jugador -- Progreso
    Jugador -- Avanzar
    Jugador -- Regresar
    Jugador -- Seleccionar
    Jugador -- Estadisticas
    Jugador -- Guardar
    Jugador -- Cargar
    Jugador -- Nuevo
    Jugador -- Opciones
    Jugador -- Tutorial

    Sistema -- Progreso
    Sistema -- Verificar
    Sistema -- Avanzar
    Sistema -- Guardar

    Recolectar ..> : include Clasificar
    Descartar ..> : extend Inventario
    Comprar ..> : include Catalogo
    Avanzar ..> : include Verificar
    Comprar ..> : extend Vender
```

```mermaid
classDiagram
    %% ===== CLASES ORIGINALES (de tu diagrama) =====
    class Economia {
        +float valor
    }

    class Basura {
        +String clase
        +int cantidad
        +int espacio
        +flotar()
    }

    class Lata {
        +float peso
        -probcant()
    }

    class botella {
        +String tipos
    }

    class Tienda {
        +float precio
        +int cantidad
        #objetos()
    }

    class venta {
        -String producto
        -venta()
    }

    class mejoras {
        -bool permanente
        +float tiempo
        #mejoras()
    }

    %% ===== CLASES NUEVAS =====
    class Jugador {
        +String nombre
        +float dinero
        +int nivelActual
        +recolectar()
        +venderBasura()
        +comprarMejora()
    }

    class Inventario {
        +int capacidad
        +int espacioUsado
        +agregar()
        +vaciar()
        +estaLleno() bool
    }

    class Nivel {
        +int numero
        +float porcentajeRequerido
        +bool desbloqueado
        +bool completado
        +verificarAvance() bool
    }

    class CuerpoDeAgua {
        +String nombre
        +float porcentajeLimpieza
        +actualizarLimpieza()
        +generarBasura()
    }

    class Herramienta {
        +String nombre
        +int alcance
        +float velocidad
        +usar()
    }

    class Partida {
        +int id
        +guardar()
        +cargar()
    }

    class Progreso {
        +float porcentaje
        +calcular()
        +desbloquearNivel()
    }

    %% ===== HERENCIA (de tu diagrama) =====
    Economia <|-- Basura
    Economia <|-- Tienda
    Basura <|-- Lata
    Basura <|-- botella
    Tienda <|-- venta
    Tienda <|-- mejoras

    %% ===== ASOCIACIONES (de tu diagrama + nuevas) =====
    Tienda --> Basura : compra / valora

    Jugador "1" *-- "1" Inventario : posee
    Inventario "1" o-- "0..*" Basura : contiene
    Jugador "1" --> "0..*" mejoras : adquiere
    Jugador "1" --> "1" Tienda : interactúa
    Jugador "1" --> "0..*" Herramienta : usa
    Mejoras_Herramienta

    Nivel "1" *-- "1" CuerpoDeAgua : tiene
    CuerpoDeAgua "1" o-- "0..*" Basura : genera
    Jugador "1" --> "1" Nivel : juega
    Nivel "1" --> "1" Progreso : mide
    Progreso ..> CuerpoDeAgua : lee porcentaje
    Partida "1" --> "1" Jugador : guarda
    Partida "1" --> "1..*" Nivel : registra
```
