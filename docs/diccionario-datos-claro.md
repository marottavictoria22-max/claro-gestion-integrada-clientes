# Diccionario de Datos - Gestión Integrada Clientes Claro AMX

## 1. Entidad: Cliente
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_cliente | INT | PK | Identificador único |
| dni | VARCHAR(15) | UK | DNI/CUIT |
| nombre_completo | VARCHAR(100) | - | Nombre y apellido |
| email | VARCHAR(100) | - | Email contacto |
| telefono | VARCHAR(20) | - | Tel de contacto |
| id_plan | INT | FK | Plan actual |
| estado | ENUM | - | Activo, Suspendido, Baja |

## 2. Entidad: Plan
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_plan | INT | PK | ID Plan |
| nombre_plan | VARCHAR(50) | - | Ej: Control 5GB |
| precio_mensual | DECIMAL(10,2) | - | Precio |
| gb_datos | INT | - | Gigas incluidos |
| minutos | INT | - | Minutos libres |
| tipo | ENUM | - | Prepago, Postpago, Control |

## 3. Entidad: SIM
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_sim | INT | PK | ID SIM |
| iccid | VARCHAR(20) | UK | Código SIM |
| imsi | VARCHAR(20) | UK | Código IMSI |
| id_cliente | INT | FK | Dueño |
| estado_stock | ENUM | - | Disponible, Asignada, Bloqueada |

## 4. Entidad: Factura
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_factura | INT | PK | Nro Factura |
| id_cliente | INT | FK | Cliente |
| periodo | DATE | - | Periodo facturado |
| monto_total | DECIMAL(10,2) | - | Total a pagar |
| estado_pago | ENUM | - | Paga, Pendiente, Vencida |

## 5. Entidad: Ticket (Soporte)
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_ticket | INT | PK | ID Ticket |
| id_cliente | INT | FK | Cliente |
| tipo_reclamo | VARCHAR(50) | - | Portabilidad, Facturación |
| prioridad | ENUM | - | Alta, Media, Baja |
| estado | ENUM | - | Abierto, En curso, Cerrado |

## 6. Entidad: Usuario (Interno Claro)
| Campo | Tipo | PK/FK | Descripción |
| :--- | :--- | :--- | :--- |
| id_usuario | INT | PK | ID Usuario interno |
| legajo | VARCHAR(20) | UK | Legajo empleado |
| rol | ENUM | - | Comercial, Soporte, Admin |
| sucursal | VARCHAR(50) | - | Sucursal |

## KPIs de Control - Entrega 4
- KPI1: % Altas de plan < 24hs (Meta >95%)
- KPI2: % Stock SIM disponible (Meta >90%)
- KPI3: Tickets cerrados < 48hs (Meta >85%)

## Enlaces
- Jira: [Tablero Scrum Claro AMX](https://TU-LINK-DE-JIRA.atlassian.net/jira/software/projects/SCRUM/boards/1)
- BPMN: /docs/diagrama BPMN Alta de Plan Claro AMX
