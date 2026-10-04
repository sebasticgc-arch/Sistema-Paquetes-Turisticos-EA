# 🚀 GUÍA RÁPIDA - Importar y Usar

## ⚡ 3 Pasos para tener TODO listo

### Paso 1: Descargar
```bash
git clone https://github.com/sebasticgc-arch/Sistema-Paquetes-Turisticos-EA.git
```

### Paso 2: Abrir Enterprise Architect 8.0
- Inicia EA

### Paso 3: Importar el archivo XMI
1. **Project** → **Import/Export** → **Import Package from XMI File**
2. Selecciona: `Sistema_Paquetes_Turisticos_Completo.xml`
3. Haz clic en **Import**

---

## 📊 Los 4 Diagramas Listos

Una vez importado, ve al **Project Browser** y encontrarás:

### 1️⃣ **Diagrama de Casos de Uso**
- ✅ 3 Actores (Cliente, Administrador, Operador)
- ✅ 13 Casos de Uso
- ✅ 6 Asociaciones
- ✅ 4 Relaciones <<include>>
- ✅ 2 Relaciones <<extend>>

**Para verlo dibujado:**
1. Haz clic derecho en "Sistema de Paquetes Turisticos"
2. **Add Diagram** → **Use Case**
3. Arrastra actores y casos de uso al lienzo desde el Browser
4. Arrastra **System Boundary** desde el Toolbox para envolver todo

---

### 2️⃣ **Diagrama de Actividades**
- ✅ 3 Particiones (Cliente, Sistema, Administrador)
- ✅ 17 Nodos (inicio, acciones, decisiones, merge, fin)
- ✅ 19 Flujos de control

**Para verlo dibujado:**
1. Haz clic derecho en "Reserva de Paquete Turistico"
2. **Add Diagram** → **Activity**
3. Arrastra todos los nodos al lienzo
4. Los flujos se conectan automáticamente

---

### 3️⃣ **Diagrama de Secuencia**
- ✅ 5 Lifelines (Cliente, InterfazUsuario, ControladorReservas, GestorPrecios, SistemaOperadores)
- ✅ 9 Mensajes numerados
- ✅ Flujo completo de confirmación de reserva

**Para verlo dibujado:**
1. Haz clic derecho en "Confirmacion de Reserva"
2. **Add Diagram** → **Sequence**
3. Arrastra los lifelines al lienzo
4. Los mensajes aparecen automáticamente

---

### 4️⃣ **Diagrama de Colaboración (Comunicación)**
- ✅ 4 Objetos colaborativos
- ✅ 5 Mensajes numerados
- ✅ Enlaces entre objetos

**Para verlo dibujado:**
1. Haz clic derecho en "Confirmacion - Colaboracion"
2. **Add Diagram** → **Communication**
3. Arrastra los objetos colaborativos al lienzo
4. Los enlaces numerados se dibujan automáticamente

---

## 📐 Elementos del Modelo

### Actores
- **Cliente**: Busca y reserva paquetes
- **Administrador**: Gestiona reservas
- **Operador Turístico**: Sistema externo

### Casos de Uso Principales
- Buscar paquete
- Armar paquete
- Ajustar presupuesto
- Reservar paquete
- Calcular precio
- Confirmar reserva
- Verificar disponibilidad
- Notificar operadores

### Clases (para Secuencia/Colaboración)
- **InterfazUsuario**: solicitarReserva(), mostrarConfirmacion()
- **ControladorReservas**: registrarReserva(), confirmarReserva()
- **GestorPrecios**: calcularPrecio(), aplicarRecargo()
- **SistemaOperadores**: verificarDisponibilidad(), confirmarReserva()

---

## 💰 Reglas de Cálculo

| Tipo de Cliente | Recargo |
|---|---|
| **Mayorista** | $15 fijo |
| **Nacional** | 10% del costo |
| **Extranjero** | Mayor entre 20% o $500 |

---

## 🔗 Relaciones UML

### Include (<<include>>)
- Reservar → Registrar Cliente
- Reservar → Calcular Precio
- Reservar → Verificar Disponibilidad
- Confirmar → Notificar

### Extend (<<extend>>)
- Confirmar → Confirmar Manual
- Ajustar → Recomendar Alternativas

---

## ✅ Verificación

Una vez importado, en el **Project Browser** deberías ver:

```
Sistema de Paquetes Turisticos
├── Actores (3)
├── Casos de Uso (13)
├── Clases (4)
├── Actividad: Reserva de Paquete Turistico
├── Interacción: Confirmacion de Reserva
└── Colaboración: Confirmacion - Colaboracion
```

---

## 🆘 Si algo falla

| Problema | Solución |
|---|---|
| No se abre el archivo | Verifica EA 8.0+ instalado |
| No aparecen diagramas | Los diagramas son vistas; debes crearlos arrastrando elementos |
| Faltan elementos | Expande los nodos en el Browser |
| Los flujos no se conectan | Arrastra cada nodo al lienzo individual |

---

## 📧 Listo para usar

✅ El archivo contiene **todo** lo necesario  
✅ Solo importa y crea las vistas  
✅ Los elementos ya tienen todas las relaciones  
✅ Puedes editarlos y personalizarlos como necesites

**¡Disfruta tu modelo UML! 🎉**
