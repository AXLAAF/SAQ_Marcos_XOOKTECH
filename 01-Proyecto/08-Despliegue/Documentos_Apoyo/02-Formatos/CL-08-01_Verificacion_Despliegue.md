# CL-08-01: Lista de Verificación de Despliegue — XookTech

**Proceso relacionado:** [[00-PROC-08_Despliegue]]
**Cuándo se usa:** Antes de realizar el paso a producción y después de la verificación final.
**Quién la completa:** Programador responsable / Validado por Jefe de Equipo.
**Instrucciones:** Marque con [x] cada punto. No proceda con el despliegue si hay puntos críticos (*) pendientes.

## Antes del Despliegue (Preparación)
- [ ] * **Repositorio.** El código está en la rama principal y ha pasado todas las pruebas manuales.
- [ ] * **Configuración.** Se prepararon las variables de entorno (.env) para producción.
- [ ]   **Backup.** Se realizó un respaldo (dump) de la base de datos actual antes de aplicar cambios.
- [ ] * **DNS/SSL.** El dominio apunta correctamente y el certificado SSL está activo.

## Durante el Despliegue
- [ ] * **Migraciones.** Se ejecutaron los scripts de base de datos sin errores.
- [ ] * **Permisos.** Las carpetas de escritura (storage, uploads) tienen los permisos correctos.
- [ ] * **Servicios.** Los procesos en segundo plano (workers, queues) se reiniciaron.

## Después del Despliegue (Verificación en Vivo)
- [ ] * **Happy Path.** Los flujos principales funcionan correctamente en el entorno de producción.
- [ ] * **Logs.** No hay errores críticos reportados en los logs del servidor inmediatamente después del despliegue.

## Plan de Rollback (En caso de fallo crítico)
- [ ] **Pasos de Retorno:** (Describa brevemente cómo volver a la versión anterior, ej: `git checkout v1.0`, restaurar BD).
- [ ] **Responsable Rollback:** ________________________________

---
**Programador Responsable:** ________________________________  
**Fecha:** ________________________________

**Validación Final:**
**Nombre del Jefe de Equipo:** ________________________________  
**Firma de Autorización:** ________________________________
