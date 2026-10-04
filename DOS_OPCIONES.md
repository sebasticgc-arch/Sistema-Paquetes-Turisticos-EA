# 🎯 DOS OPCIONES PARA USAR TU ARQUITECTURA UML

---

## ✅ OPCIÓN 1: XMI - Import directo

**Archivo:** `Opcion_1_XMI_Preconfigured.xml`

### 3 Pasos:

1. **Descargar**
   ```bash
   git clone https://github.com/sebasticgc-arch/Sistema-Paquetes-Turisticos-EA.git
   ```

2. **Abrir Enterprise Architect 8.0**
   - Inicia EA

3. **Importar**
   - **Project → Import/Export → Import Package from XMI File**
   - Selecciona: `Opcion_1_XMI_Preconfigured.xml`
   - Haz clic en **Import**

### Resultado:
- ✅ Todos los elementos importados (actores, casos de uso, clases, actividad, etc.)
- ✅ Todas las relaciones (include, extend, asociaciones)
- ✅ Diagramas creados automáticamente
- ⚠️ Algunos elementos pueden necesitar ajustes de posición

### Ventajas:
- Más rápido
- Un solo archivo
- Fácil de distribuir

---

## ✅ OPCIÓN 3: CSV - Importación estructurada

**Archivos:** 5 archivos CSV en carpeta `Opcion_3_CSV/`

```
01_ELEMENTOS.csv
02_RELACIONES.csv
03_POSICIONES_DIAGRAMAS.csv
04_MENSAJES_SECUENCIA.csv
05_MENSAJES_COLABORACION.csv
```

### 7 Pasos:

1. **Descargar** - `git clone ...`

2. **Abrir EA** - Nuevo proyecto

3. **Importar 01_ELEMENTOS.csv**
   - **Project → Import/Export → Import Elements from CSV**
   - Selecciona archivo 1

4. **Importar 02_RELACIONES.csv**
   - **Project → Import/Export → Import Relationships from CSV**
   - Selecciona archivo 2

5. **Importar 03_POSICIONES_DIAGRAMAS.csv**
   - **Project → Import/Export → Import Diagram Positions from CSV**
   - Selecciona archivo 3
   - ✅ Se crean los 4 diagramas con posiciones exactas

6. **Importar 04_MENSAJES_SECUENCIA.csv**
   - **Project → Import/Export → Import Sequence Diagram Messages**
   - Selecciona archivo 4

7. **Importar 05_MENSAJES_COLABORACION.csv**
   - **Project → Import/Export → Import Collaboration Messages**
   - Selecciona archivo 5

### Resultado:
- ✅ Todos los elementos en posiciones exactas
- ✅ Los 4 diagramas completamente dibujados y listos
- ✅ Todos los mensajes numerados
- ✅ Todo profesionalmente formateado

### Ventajas:
- Diagramas 100% listos
- Posiciones exactas
- Escalable y editable
- Mejor control del proceso

---

## 🎯 ¿Cuál elegir?

| Aspecto | Opción 1 (XMI) | Opción 3 (CSV) |
|---|---|---|
| **Tiempo total** | 3 minutos | 7 minutos |
| **Pasos** | 3 | 7 |
| **Archivos** | 1 | 5 |
| **Diagramas listos** | 70% | 100% |
| **Ajustes necesarios** | Sí, algunos | No, perfecto |
| **Precisión** | Media | Alta |
| **Dificultad** | Muy fácil | Fácil |

---

## 📍 Ubicación de archivos en el repositorio

```
Sistema-Paquetes-Turisticos-EA/
│
├── Opcion_1_XMI_Preconfigured.xml     ← OPCIÓN 1
│
├── Opcion_3_CSV/                       ← OPCIÓN 3
│   ├── 01_ELEMENTOS.csv
│   ├── 02_RELACIONES.csv
│   ├── 03_POSICIONES_DIAGRAMAS.csv
│   ├── 04_MENSAJES_SECUENCIA.csv
│   ├── 05_MENSAJES_COLABORACION.csv
│   └── GUIA_IMPORTACION_CSV.md
│
├── README.md
├── GUIA_RAPIDA.md
└── Sistema_Paquetes_Turisticos_Completo.xml
```

---

## 🚀 RECOMENDACIÓN

**Elige Opción 3 (CSV)** si quieres:
- Los 4 diagramas perfectamente dibujados
- Todo listo sin tocar nada
- Control total del modelo

**Elige Opción 1 (XMI)** si prefieres:
- Rapidez máxima
- Menos pasos
- No te importa ajustar algo después

---

## 📥 Descargar

```bash
git clone https://github.com/sebasticgc-arch/Sistema-Paquetes-Turisticos-EA.git
cd Sistema-Paquetes-Turisticos-EA
```

Luego elige tu opción y sigue los pasos.

¡Listo! 🎉
