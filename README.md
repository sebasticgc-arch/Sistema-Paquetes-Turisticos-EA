# Sistema de Gestión de Paquetes Turísticos - Arquitectura UML Completa

## 📋 Descripción

Este repositorio contiene la **arquitectura completa en UML** para un sistema de gestión de paquetes turísticos, con 4 diagramas listos para importar en **Enterprise Architect 8.0**.

El sistema permite a clientes buscar, armar y reservar paquetes (vuelos, hoteles, traslados) ajustados a su presupuesto, mientras que los administradores gestionan estas reservas y se comunican con operadores turísticos externos.

---

## 📦 Contenido del Archivo XMI

El archivo `Sistema_Paquetes_Turisticos_Completo.xml` contiene:

### 1. **Diagrama de Casos de Uso** 
   - **Actores:** Cliente, Administrador, Operador Turístico
   - **Casos de Uso:** 13 casos incluyendo Buscar, Armar, Ajustar, Reservar, Calcular Precio, Confirmar, Verificar Disponibilidad, Notificar, etc.
   - **Relaciones:** 
     - Asociaciones (Actor → Caso de Uso)
     - `<<include>>` (4 incluencias)
     - `<<extend>>` (2 extensiones)

### 2. **Diagrama de Actividades**
   - **Flujo Completo:** Desde búsqueda hasta confirmación de reserva
   - **Particiones (Calles):** Cliente, Sistema, Administrador
   - **Nodos:** 
     - Inicio/Final
     - Acciones: Buscar, Comparar, Armar, Verificar, Calcular
     - Decisiones: "¿Se ajusta al presupuesto?", "¿Hay disponibilidad?", "¿Tipo de cliente?"
     - Recargos: Mayorista ($15), Nacional (10%), Extranjero (max 20% o $500)
     - Merge y notificación

### 3. **Diagrama de Secuencia**
   - **Escenario:** Confirmación de Reserva
   - **Actores/Objetos:**
     - Cliente
     - InterfazUsuario
     - ControladorReservas
     - GestorPrecios
     - SistemaOperadoresExternos
   - **Mensajes:** 10 mensajes numerados mostrando flujo de llamadas síncronas y respuestas

### 4. **Diagrama de Colaboración (Comunicación)**
   - **Mismo escenario** que Secuencia, pero enfocado en **enlaces entre objetos**
   - **Estructura:** 4 objetos colaborativos con mensajes numerados

---

## 🚀 Cómo Importar en Enterprise Architect 8.0

### Paso 1: Descargar el archivo
```bash
git clone https://github.com/sebasticgc-arch/Sistema-Paquetes-Turisticos-EA.git
cd Sistema-Paquetes-Turisticos-EA
```

### Paso 2: Abrir Enterprise Architect 8.0

### Paso 3: Importar el XMI
1. En EA, ve a: **Project → Import/Export → Import Package from XMI File**
2. Selecciona `Sistema_Paquetes_Turisticos_Completo.xml`
3. Elige una ubicación en tu proyecto (ej: raíz)
4. Haz clic en **Import**

### Paso 4: Visualizar los Diagramas
Una vez importado, en el **Project Browser** verás:
- Paquete: "Sistema de Paquetes Turisticos"
  - Actores, Casos de Uso, Clases
  - Actividad: "Reserva de Paquete Turistico"
  - Interacción: "Confirmacion de Reserva - Secuencia"
  - Colaboración: "Confirmacion de Reserva - Colaboracion"

### Paso 5: Crear los Diagramas (Hacer Dibujos)
Para **ver los diagramas dibujados**, debes crear vistas:

#### Para Casos de Uso:
1. Haz clic derecho en "Sistema de Paquetes Turisticos" → **Add Diagram → Use Case**
2. Arrastra desde el Browser:
   - **Actores** (Cliente, Administrador, Operador)
   - **Casos de Uso** (todos)
3. Arrastra desde el Toolbox:
   - **System Boundary** (cuadro que envuelve los casos)
4. Las **asociaciones e includes/extends** ya están en el modelo; EA las dibujará automáticamente cuando conectes los elementos

#### Para Actividades:
1. Haz clic derecho en la Actividad "Reserva de Paquete Turistico" → **Add Diagram → Activity**
2. Arrastra los **nodos** desde el Browser al lienzo
3. Los flujos ya existen; deberían aparecer automáticamente

#### Para Secuencia:
1. Haz clic derecho en la Interacción "Confirmacion de Reserva - Secuencia" → **Add Diagram → Sequence**
2. Arrastra los **lifelines** desde el Browser
3. Los mensajes ya están definidos y deberían mostrarse automáticamente

#### Para Colaboración:
1. Haz clic derecho en la Colaboración → **Add Diagram → Communication**
2. Arrastra los **objetos colaborativos** desde el Browser
3. Los enlaces numerados se dibujarán automáticamente

---

## 📐 Elementos del Modelo

### Actores
| ID | Nombre | Descripción |
|-----|--------|-------------|
| ACTOR_CLIENTE | Cliente | Persona que busca y reserva paquetes |
| ACTOR_ADMIN | Administrador | Gestiona reservas y operadores |
| ACTOR_OPERADOR | Operador Turístico | Sistema externo que verifica disponibilidad |

### Casos de Uso Principales
| ID | Nombre | Descripción |
|-----|--------|-------------|
| UC_BUSCAR | Buscar paquete turístico | Cliente busca destinos y fechas |
| UC_ARMAR | Armar paquete personalizado | Selecciona vuelos, hotel, traslados |
| UC_AJUSTAR | Ajustar paquete al presupuesto | Adapta opciones al monto disponible |
| UC_RESERVAR | Reservar paquete | Inicia el proceso de reserva |
| UC_CALCULAR | Calcular precio final | Suma costos y aplica recargos |
| UC_CONFIRMAR | Confirmar reserva | Cierra la transacción |
| UC_VERIFICAR | Verificar disponibilidad | Consulta a operadores externos |
| UC_NOTIFICAR | Notificar confirmación | Envía datos a operadores |

### Clases para Secuencia/Colaboración
| ID | Nombre | Operaciones |
|-----|--------|-----------|
| CLASS_UI | InterfazUsuario | solicitarReserva(), mostrarConfirmacion() |
| CLASS_CTL | ControladorReservas | registrarReserva(), confirmarReserva() |
| CLASS_PRC | GestorPrecios | calcularPrecio(), aplicarRecargo() |
| CLASS_OPE | SistemaOperadoresExternos | verificarDisponibilidad(), confirmarReserva() |

---

## 💰 Reglas de Cálculo de Precio

El sistema aplica recargos según el tipo de cliente:

### Clientes Mayoristas
- Recargo fijo: **$15**

### Clientes Nacionales
- Recargo: **10% del costo original**

### Clientes Extranjeros
- Recargo: **Mayor entre 20% del costo original o $500**

---

## 🔗 Relaciones UML Definidas

### Include (<<include>>)
- Reservar Paquete → Registrar Cliente
- Reservar Paquete → Calcular Precio Final
- Reservar Paquete → Verificar Disponibilidad
- Confirmar Reserva → Notificar Confirmación

### Extend (<<extend>>)
- Confirmar Reserva → Confirmar Reserva Manualmente
- Ajustar Paquete → Recomendar Alternativas

---

## 📊 Flujo de Secuencia - Confirmación de Reserva

```
Cliente → InterfazUsuario → ControladorReservas → GestorPrecios
                              ↓
                        SistemaOperadoresExternos
                              ↓
                        [Verificación y cálculo]
                              ↓
                        Retorna confirmación
```

**Mensajes:**
1. solicitarReserva(paquete)
2. registrarReserva(paquete, cliente)
3. calcularPrecio(paquete, tipoCliente)
4. verificarDisponibilidad(paquete)
5. confirmarReserva(reserva)
6. mostrarConfirmacion(precio, estado)

---

## 📝 Notas Importantes

- ✅ El archivo XMI está validado para EA 8.0
- ✅ Todos los elementos están creados en el modelo
- ✅ Las relaciones y conexiones ya existen
- ⚠️ Los diagramas **NO están pre-dibujados** (esto es intencional), pero puedes crearlos fácilmente arrastrando elementos
- ⚠️ Si necesitas que los diagramas estén completamente dibujados con coordenadas, contacta para una versión mejorada

---

## 🛠️ Solución de Problemas

### El archivo no abre en EA
- Verifica que uses **EA 8.0 o superior**
- Intenta: **File → Import → Import Package from XMI**

### Los elementos se importan pero no hay diagramas
- Los diagramas son vistas, no datos. Debes **crear** vistas nuevas y arrastrar los elementos importados

### Falta algún elemento
- Revisa que los **nodos, lifelines y mensajes** estén en el Browser
- Pueden estar ocultos; expande los nodos en el árbol

---

## 📧 Contacto

Para preguntas o modificaciones al modelo, contacta al arquitecto de software.

---

**Última actualización:** Octubre 2026  
**Versión:** 1.0  
**Formato:** XMI (XML Metadata Interchange)  
**Herramienta:** Enterprise Architect 8.0+
