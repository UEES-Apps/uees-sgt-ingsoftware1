# SGT - Sistema de Gestión de Tutorías

Repositorio del proyecto integrador de **Ingeniería de Software I (UCOM304)** - Universidad Espíritu Santo.

**Estudiante:** Marlon Tomás Ramírez Morán
**Docente:** Ph.D. Jaime Paul Sayago Heredia
**Paralelo:** 1

## ¿Qué es el SGT?

Una plataforma web/móvil para automatizar la solicitud, agendamiento, ejecución y seguimiento de tutorías académicas: un estudiante solicita una tutoría, un tutor gestiona su disponibilidad y confirma o rechaza solicitudes, y la coordinación académica obtiene reportes de cumplimiento.

## Estructura del repositorio

```
uees-sgt-ingsoftware1/
├── diagramas/                                      Diagramas UML (código fuente PlantUML)
│   ├── diagrama_clases_Ae5_SGT.puml                Diagrama de clases (versión final, Ae5)
│   ├── diagrama_secuencia_SGT.puml                 SEQ01 — Reservar tutoría
│   └── diagrama_secuencia_SEQ02_cancelar_SGT.puml  SEQ02 — Cancelar una reserva activa
│
└── README.md
```

## Cómo renderizar los diagramas

Los archivos `.puml` se pueden visualizar de varias formas:

- **En línea:** pega el contenido en [PlantUML Web Server](https://www.plantuml.com/plantuml/uml/).
- **VS Code:** instala la extensión "PlantUML" y usa `Alt+D` para previsualizar.
- **Localmente:** con Java instalado, descarga `plantuml.jar` y ejecuta:
  ```
  java -jar plantuml.jar -tpng diagramas/diagrama_clases_Ae5_SGT.puml
  ```

## Notas de diseño relevantes

- El modelo trata **"Tutoría"** como sinónimo de una `Reserva` confirmada, no como clase independiente.
- **`ControladorReserva`** y **`PantallaReserva`** son clases de control/interfaz (no de dominio), documentadas explícitamente para no confundirlas con conceptos del negocio.
- La política de cancelación exige **24 horas de antelación**; si no se cumple, la reserva se registra como **"Inasistencia"** en vez de "Cancelada".
