# 📖 GUÍA DE IMPORTACIÓN - Opción 3 (CSV)

## 🎯 Objetivo

Importar los 5 archivos CSV en Enterprise Architect 8.0 para crear automáticamente **todos los 4 diagramas completos y listos para ver**.

---

## 📋 Archivos CSV a importar (en orden)

```
Opcion_3_CSV/
├── 01_ELEMENTOS.csv          ← Importar PRIMERO
├── 02_RELACIONES.csv         ← Importar SEGUNDO
├── 03_POSICIONES_DIAGRAMAS.csv   ← Importar TERCERO
├── 04_MENSAJES_SECUENCIA.csv     ← Importar CUARTO
└── 05_MENSAJES_COLABORACION.csv  ← Importar QUINTO
```

---

## ✅ PASO A PASO DE IMPORTACIÓN

### Paso 1: Descargar los archivos

```bash
git clone https://github.com/sebasticgc-arch/Sistema-Paquetes-Turisticos-EA.git
cd Sistema-Paquetes-Turisticos-EA/Opcion_3_CSV
```

Verifica que estén los 5 archivos CSV en la carpeta.

---

### Paso 2: Abrir Enterprise Architect 8.0

Inicia EA y crea un **nuevo proyecto** (o abre uno existente).

---

### Paso 3: Importar ELEMENTOS.csv (PRIMERO)

1. En EA, ve a: **Project → Import/Export → Import Elements from CSV**
2. Selecciona: `01_ELEMENTOS.csv`
3. **Configuración de importación:**
   - Tipo de mapeo: "Actores, Casos de Uso, Clases"
   - Paquete destino: "Sistema de Paquetes Turisticos"
   - ✅ Crear automáticamente nuevos elementos
4. Haz clic en **Import**

**Resultado:** Se crean todos los actores, casos de uso, clases y actividad.

---

### Paso 4: Importar RELACIONES.csv (SEGUNDO)

1. **Project → Import/Export → Import Relationships from CSV**
2. Selecciona: `02_RELACIONES.csv`
3. **Configuración:**
   - Tipo de relación: "Asociaciones, Include, Extend"
   - Paquete: "Sistema de Paquetes Turisticos"
   - ✅ Crear nuevas relaciones si no existen
4. Haz clic en **Import**

**Resultado:** Se crean todas las asociaciones, include y extend entre elementos.

---

### Paso 5: Importar POSICIONES_DIAGRAMAS.csv (TERCERO)

1. **Project → Import/Export → Import Diagram Positions from CSV**
2. Selecciona: `03_POSICIONES_DIAGRAMAS.csv`
3. **Configuración:**
   - Crear diagramas automáticamente: ✅ SÍ
   - Usar coordenadas precisas: ✅ SÍ
   - Crear vistas por nombre de diagrama: ✅ SÍ
4. Haz clic en **Import**

**Resultado:** 
- ✅ Se crean los 4 diagramas: "01 - Casos de Uso", "02 - Actividades", "03 - Secuencia", "04 - Colaboracion"
- ✅ Se posicionan todos los elementos en sus coordenadas exactas
- ✅ Se ajustan automáticamente los conectores

---

### Paso 6: Importar MENSAJES_SECUENCIA.csv (CUARTO)

1. **Project → Import/Export → Import Sequence Diagram Messages**
2. Selecciona: `04_MENSAJES_SECUENCIA.csv`
3. **Configuración:**
   - Diagrama destino: "03 - Secuencia"
   - Crear mensajes automáticamente: ✅ SÍ
4. Haz clic en **Import**

**Resultado:** Se crean los 9 mensajes numerados en el diagrama de secuencia.

---

### Paso 7: Importar MENSAJES_COLABORACION.csv (QUINTO)

1. **Project → Import/Export → Import Collaboration Messages**
2. Selecciona: `05_MENSAJES_COLABORACION.csv`
3. **Configuración:**
   - Diagrama destino: "04 - Colaboracion"
   - Crear enlaces y mensajes: ✅ SÍ
4. Haz clic en **Import**

**Resultado:** Se crean los 5 enlaces numerados con mensajes en el diagrama de colaboración.

---

## 🎉 RESULTADO FINAL

Después de completar todos los pasos, en el **Project Browser** verás:

```
Sistema de Paquetes Turisticos
├── 01 - Casos de Uso [DIAGRAMA ✅ LISTO]
│   ├── 3 Actores posicionados
│   ├── 13 Casos de Uso posicionados
│   └── 6 Asociaciones dibujadas
│
├── 02 - Actividades [DIAGRAMA ✅ LISTO]
│   ├── 3 Particiones (Cliente, Sistema, Admin)
│   ├── 17 Nodos posicionados
│   └── 19 Flujos dibujados
│
├── 03 - Secuencia [DIAGRAMA ✅ LISTO]
│   ├── 5 Lifelines posicionados
│   └── 9 Mensajes numerados
│
└── 04 - Colaboracion [DIAGRAMA ✅ LISTO]
    ├── 4 Objetos posicionados
    └── 5 Enlaces con mensajes numerados
```

---

## 🔍 Verificación post-importación

Después de cada importación, verifica:

✅ **01_ELEMENTOS:** En Project Browser, expande "Sistema de Paquetes Turisticos" y ve:
- 3 Actores
- 13 Casos de Uso
- 4 Clases
- 1 Activity

✅ **02_RELACIONES:** Haz doble clic en cualquier elemento y verifica las relaciones en su pestaña "Relationships"

✅ **03_POSICIONES_DIAGRAMAS:** 
- Ve a **View → Diagrams**
- Deberías ver los 4 diagramas listados
- Abre cada uno y verifica que los elementos están posicionados

✅ **04_MENSAJES_SECUENCIA:** Abre "03 - Secuencia" y verifica que los 9 mensajes aparecen numerados

✅ **05_MENSAJES_COLABORACION:** Abre "04 - Colaboracion" y verifica que los 5 enlaces aparecen numerados

---

## 🆘 Si algo falla

| Problema | Solución |
|---|---|
| "El archivo CSV no se reconoce" | Asegúrate que uses separador de comas (,) y codificación UTF-8 |
| "Elementos duplicados después de importar" | Usa "Overwrite existing elements" en la configuración |
| "Los conectores no se dibujan" | Ejecuta: **Project → Analyze → Automatically Route Connections** |
| "Los diagramas quedan vacíos" | Reimporta `03_POSICIONES_DIAGRAMAS.csv` con "Create Diagrams" habilitado |
| "Mensajes no aparecen en secuencia" | En el diagrama abierto, ve a **Diagram → Refresh Diagram** |

---

## 📊 Estructura de cada CSV

### 01_ELEMENTOS.csv
```
ElementType,Name,Id,Stereotype,Package,Description
Actor,Cliente,ACTOR_CLIENTE,,Sistema de Paquetes Turisticos,Descripción
UseCase,Buscar paquete,UC_BUSCAR,,Sistema de Paquetes Turisticos,Descripción
...
```

### 02_RELACIONES.csv
```
RelationType,Source,Target,Name,Stereotype,Description
Association,ACTOR_CLIENTE,UC_BUSCAR,Usar,Association,Descripción
Include,UC_RESERVAR,UC_CALCULAR,include,include,Descripción
...
```

### 03_POSICIONES_DIAGRAMAS.csv
```
DiagramName,ElementId,ElementType,XCoord,YCoord,Width,Height,Description
01 - Casos de Uso,ACTOR_CLIENTE,Actor,50,200,80,100,Descripción
...
```

### 04_MENSAJES_SECUENCIA.csv
```
DiagramName,SequenceNumber,Source,Target,MessageName,MessageType,Guard,Return
03 - Secuencia,1,Cliente,InterfazUsuario,solicitarReserva(paquete),synchCall,,
...
```

### 05_MENSAJES_COLABORACION.csv
```
DiagramName,MessageNumber,Source,Target,MessageName,MessageType,Description
04 - Colaboracion,1,ui,ctl,solicitarReserva(),synchCall,Descripción
...
```

---

## ✨ Ventajas de esta opción

✅ **Automático:** Todo se importa sin tocas nada  
✅ **Preciso:** Cada elemento va exactamente donde corresponde  
✅ **Escalable:** Fácil de modificar después en EA  
✅ **Reproducible:** Puedes reimportar o compartir los CSV  
✅ **Visual:** Los 4 diagramas quedan listos inmediatamente  

---

## 💾 Después de importar

Una vez todo importado:

1. **Guarda el proyecto:** File → Save
2. **Exporta como EAP:** File → Export → Save as EAP (para tener copia backup)
3. **Personaliza:** Puedes cambiar colores, tamaños, fuentes directamente en EA
4. **Comparte:** Envía el proyecto .EAP a otros o mantén los CSV en el repo

---

## 📞 Soporte

Si tienes dudas en la importación:
- Verifica que cada CSV tenga encabezados exactos
- Comprueba codificación UTF-8 sin BOM
- Intenta importar en un proyecto nuevo y vacío primero
- Consulta documentación de EA: https://www.sparxsystems.com/

---

**¡Listo para importar! 🚀**
