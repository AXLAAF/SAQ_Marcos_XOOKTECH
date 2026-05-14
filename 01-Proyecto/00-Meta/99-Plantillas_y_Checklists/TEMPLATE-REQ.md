---
id: REQ-XX
titulo: [Titulo del Requerimiento]
version: "1.0"
estado: Borrador
prioridad: [Alta / Media / Baja]
tipo: [Funcional / No Funcional]
modulo: [Carga / Catalogo / Previsualizacion]
responsable: Axel Morales
fuente: [[05-Contrato_Desarrollo]] / [[04-Minuta_Entrevista_Recuperacion]]
---

# REQ-XX: [Titulo del Requerimiento]

## 1. Descripcion General
[Que debe hacer el sistema. Perspectiva del usuario, sin tecnicismos.]

## 2. Reglas de Negocio
- RN-XX-01: [Regla cuantificada. Ej: El archivo no puede superar 10 MB.]
- RN-XX-02: ...

## 3. Precondiciones
- [Estado del sistema o del actor requerido para iniciar]

## 4. Flujo Principal (Happy Path)
1. El [Actor] realiza [Accion].
2. El sistema [Respuesta observable].
3. ...

## 5. Flujos Alternativos / Excepcion
| ID | Condicion | Respuesta del Sistema |
| :--- | :--- | :--- |
| FA-01 | [Condicion] | [Accion] |
| FE-01 | [Error] | [Mensaje de error] |

## 6. Criterios de Aceptacion (BDD)
| CA-ID | Dado | Cuando | Entonces |
| :--- | :--- | :--- | :--- |
| CA-01 | [Contexto] | [Accion] | [Resultado esperado] |

## 7. Restricciones Tecnicas
- [Ej: Rendimiento < 2s, Formato PNG, etc.]

## 8. Trazabilidad
- Fuente: [[05-Contrato_Desarrollo]]
- Casos de Prueba: [[CP-XX_Nombre]]
- Change Requests: [[CR-XX_Nombre]]

---
*Ultima actualizacion: {{date}}*
