[REATMI.md](https://github.com/user-attachments/files/28529664/REATMI.md)
# PetroData Casanare S.A.S. — Sistema de Producción Diaria

Aplicación de consola desarrollada en **Java** para el registro y análisis de la producción diaria de barriles de petróleo durante un mes (30 días).

---

## Descripción

`PetroDataApp` permite a operadores de campo ingresar, consultar y analizar los datos de producción de un pozo petrolero. Está diseñada como una herramienta de escritorio liviana, sin dependencias externas, orientada a personal técnico en campo.

---

## Funcionalidades

| Opción | Descripción |
|--------|-------------|
| 1 | Ingresar producción diaria de los 30 días del mes |
| 2 | Ver estadísticas: total, promedio, día máximo y mínimo |
| 3 | Buscar el primer día que superó una meta definida por el usuario |
| 4 | Ver reporte completo con clasificación por nivel de producción |
| 5 | Salir del sistema |

### Clasificación de producción (Opción 4)

| Nivel | Rango |
|-------|-------|
| ALTO  | ≥ 1500 bbl |
| MEDIO | 800 – 1499 bbl |
| BAJO  | 1 – 799 bbl |
| (omitido) | 0 bbl |

---

## Requisitos

- **Java** 8 o superior
- No requiere librerías externas

---

## Compilación y ejecución

```bash
# Compilar
javac PetroDataApp.java

# Ejecutar
java PetroDataApp
```

---

## Estructura del código

```
PetroDataApp.java
├── main()           → Bucle principal del menú
├── mostrarMenu()    → Imprime el menú de opciones
├── ingresarDatos()  → Captura y valida los 30 valores diarios (0–5000 bbl)
├── verEstadisticas() → Calcula total, promedio, máximo y mínimo
├── buscarMeta()     → Busca el primer día que supera una meta ingresada
└── verReporte()     → Imprime reporte completo omitiendo días con 0 bbl
```

---

## Validaciones

- Producción diaria: solo acepta valores entre **0 y 5000 bbl**
- Meta de búsqueda: no puede ser negativa
- Las opciones 2, 3 y 4 requieren que se hayan ingresado datos previamente (opción 1)

---

## Ejemplo de salida — Estadísticas

```
=== OPCION 2 - Estadisticas ===
Total mes   : 42350 bbl
Promedio dia: 1411.67 bbl
Maximo      : Dia 12 -> 4800 bbl
Minimo      : Dia 5  -> 0 bbl
```

## Ejemplo de salida — Reporte

```
=== OPCION 4 - Reporte completo ===
Dia  5: produccion 0 bbl - omitido. (continue)
Dia  1 | 1500 bbl | [ALTO]
Dia  2 |  950 bbl | [MEDIO]
Dia  3 |  420 bbl | [BAJO]
```

---

## Autor

Desarrollado para **PetroData Casanare S.A.S.** — Yopal, Casanare, Colombia.
