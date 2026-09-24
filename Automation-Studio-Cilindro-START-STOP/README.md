# Control de cilindro neumático con START/STOP – Automation Studio

## Descripción

Proyecto de automatización neumática desarrollado en **Automation Studio**.

El sistema controla un cilindro de doble efecto mediante una válvula direccional accionada por dos solenoides:

- **R1:** avance del cilindro.
- **R2:** retroceso del cilindro.
- **Sensor 1:** detecta cilindro extendido.
- **Sensor 2:** detecta cilindro retraído.
- **B1:** habilitación y enclavamiento de marcha.
- **START:** inicia el sistema.
- **STOP:** detiene el sistema.
- **Lámpara verde:** indica avance del cilindro.
- **Lámpara roja:** indica retroceso del cilindro.

## Secuencia de funcionamiento

1. Se presiona **START** y se activa B1.
2. El cilindro avanza mediante **R1**.
3. Mientras avanza: **R1 = 1**, Verde = ON y Roja = OFF.
4. Al llegar al final, **Sensor 1** detecta la posición.
5. R1 se desactiva y se activa **R2**.
6. El cilindro retrocede: **R2 = 1**, Roja = ON y Verde = OFF.
7. Al llegar a la posición inicial, **Sensor 2** detecta el cilindro.
8. R2 se desactiva y el sistema queda listo para un nuevo ciclo.

## Interbloqueo

Se utilizan contactos normalmente cerrados de **R1 y R2** para evitar que ambas salidas se activen simultáneamente.

```text
R1 = 1 → R2 = 0 → Verde = ON
R2 = 1 → R1 = 0 → Roja = ON
```

## Tecnologías

- Automation Studio
- Neumática y electroneumática
- Lógica Ladder
- Sensores de posición
- Válvula direccional
- Solenoides
- Control START/STOP
- Señalización mediante lámparas piloto

## Objetivo

Practicar diseño, simulación y diagnóstico de un sistema electroneumático con arranque, paro, enclavamiento, sensores, avance, retroceso e interbloqueo de salidas.

## Estructura recomendada

```text
01-Cilindro-START-STOP/
├── Automation-Studio/
├── Images/
│   ├── circuito.png
│   └── grafcet.png
└── README.md
```

## Autor

**Luis Fco. Castillo**

Proyecto de práctica – Automatización Industrial

## Nota de seguridad

Proyecto con fines educativos. Antes de implementar una lógica similar en una máquina real, deben verificarse paro de emergencia, enclavamientos, condiciones de seguridad y normativa aplicable.
