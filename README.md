# Auditoría de Ciberseguridad y Evaluación de Riesgos

Este repositorio contiene la documentación de evaluación de controles de seguridad, análisis de riesgos de TI e identificación de brechas de cumplimiento normativo para infraestructura corporativa y comercio electrónico.

---

## Proyecto: Evaluaciones de Seguridad Interna y Cumplimiento Normativo (Botium Toys)

### 1. Resumen Ejecutivo
**Botium Toys** cuenta con una sede física (oficina, escaparate y almacén) y un canal de comercio electrónico en expansión con clientes en EE. UU. y la Unión Europea. 

A medida que crece la infraestructura de TI para dar soporte a las ventas internacionales, se realizó una auditoría interna basada en el **NIST Cybersecurity Framework (NIST CSF)** para evaluar la postura de seguridad actual, identificar vulnerabilidades en activos críticos y determinar el nivel de cumplimiento frente a los estándares **PCI DSS**, **GDPR** y **SOC**.

---

### 2. Matriz de Controles de Seguridad (*Controls Checklist*)

| Control / Módulo de Seguridad | Estado | Diagnóstico Térmico / Brecha Detectada |
| :--- | :---: | :--- |
| **Least Privilege** | **No** | Ausencia de restricciones de acceso por función. Todo el personal tiene visibilidad completa sobre los activos de datos. |
| **Role-Based Access Control (RBAC)** | **No** | No existen matrices de acceso ni asignación de permisos definidos por perfil de puesto. |
| **Password Manager** | **No** | Inexistencia de un gestor corporativo centralizado; la gestión de credenciales queda a criterio individual del empleado. |
| **Multi-Factor Authentication (MFA)** | **No** | Los accesos a sistemas críticos no requieren validación de segundo factor. |
| **Antivirus Software** | **Sí** | Desplegado y operativo en los puntos finales (*endpoints*) gestionados por TI. |
| **Automated Software Updates** | **No** | La gestión de parches se ejecuta manualmente, dejando la infraestructura expuesta a vulnerabilidades conocidas. |
| **Firewall** | **Sí** | Cortafuegos perimetral activo para filtrado e inspección de tráfico de red. |
| **Disabled Unused Virtual Ports/Services** | **No** | Interfases y puertos virtuales no utilizados permanecen abiertos, ampliando la superficie de ataque. |
| **Physical Security** | **Sí** | Controles de acceso físico e instalaciones aseguradas en almacén, tienda y oficinas. |
| **Data Encryption** | **No** | La información de identificación personal (PII) y los registros financieros se almacenan en texto plano (*cleartext*). |
| **Backups** | **Sí** | Respaldos periódicos de datos configurados y operativos. |
| **Intrusion Detection System (IDS)** | **No** | Sin capacidad de monitoreo de red ni telemetría en tiempo real para detección de tráfico anómalo. |

---

### 3. Evaluación de Cumplimiento y Normativa (*Compliance Checklist*)

| Estándar / Regulativo | Estado | Diagnóstico de Cumplimiento |
| :--- | :---: | :--- |
| **PCI DSS** | **No** | Procesamiento y almacenamiento de datos de tarjetas de pago en línea en texto plano, sin cifrado ni controles de acceso segmentados. |
| **GDPR** | **No** | Captura y almacenamiento de PII de ciudadanos de la UE sin mecanismos de cifrado, anonimización ni garantías de privacidad desde el diseño. |
| **SOC Type 1 / SOC Type 2** | **No** | Ausencia de políticas formales, controles auditables y documentación sobre la confidencialidad e integridad del procesamiento de datos. |

---

### 4. Plan de Remediación y Prioridades

1. **Cifrado en Reposo y en Tránsito:** Implementar cifrado de base de datos (AES-256) y forzar protocolos TLS 1.3 en el portal web para alineación inmediata con PCI DSS y GDPR.
2. **Implementación de RBAC y MFA:** Segmentar accesos bajo el principio de mínimo privilegio y requerir MFA obligatorio en todos los sistemas.
3. **Gestión de Vulnerabilidades y Parches:** Automatizar la actualización de software/firmware y cerrar puertos o servicios no requeridos.
4. **Despliegue de IDS/SIEM:** Implementar monitoreo de red perimetral para detección temprana de intrusiones y análisis de eventos de seguridad.
