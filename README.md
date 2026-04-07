# DevOps Project: High-Availability Hotfix 🛠️

> **Contexto de Operación:** Este repositorio gestiona una corrección crítica (Hotfix) bajo estándares de automatización de nivel industrial, garantizando la estabilidad del sistema mediante flujos de trabajo controlados.

## 📝 Descripción del Proyecto
Aplicación de prácticas de **DevOps** para la automatización de despliegues y gestión de calidad. Este proyecto implementa un pipeline robusto de CI/CD que valida cada cambio antes de su integración a ramas productivas.

---

## 🏗️ Gobernanza del Desarrollo

### 1. Naming de Ramas (Git Flow)
Para mantener la trazabilidad, las ramas deben seguir esta nomenclatura:
* `hotfix/descripción-breve`: Correcciones urgentes en producción.
* `feature/nombre-funcionalidad`: Desarrollo de nuevas características.
* `bugfix/ticket-id`: Resolución de errores menores detectados en desarrollo.

### 2. Convenciones de Commits (Conventional Commits)
Se requiere el uso de prefijos para facilitar la generación de changelogs automáticos:
* `fix:` Corrección de errores (relacionado con el Hotfix actual).
* `feat:` Nueva funcionalidad.
* `docs:` Cambios solo en la documentación.
* `test:` Añadir o corregir pruebas existentes.

*Ejemplo:* `fix: corregir desbordamiento de memoria en el módulo de carga`

### 3. Flujos de Merge
* **Integración:** Todo merge hacia `develop` o `main` debe ser procesado mediante **Pull Requests (PR)**.
* **Requisito de CI:** No se permite el merge si el **Workflow de GitHub Actions** (Linter + Tests) no está en estado "Pass" (verde).
* **Estrategia:** Se prioriza el uso de *Squash and Merge* para mantener un historial de commits limpio y lineal.

### 4. Estrategias de Revisión (Code Review)
* **Aprobación Obligatoria:** Al menos un par debe revisar el código antes del despliegue.
* **Checklist de Revisión:**
    * Cumplimiento de estándares PEP8 (Linter).
    * Cobertura de pruebas unitarias satisfactoria.
    * Ausencia de credenciales expuestas en el código.

---

## 🤖 Pipeline de Automatización (Workflow)
El archivo `.github/workflows/ci-cd.yml` gestiona automáticamente:
1.  **Static Analysis:** Validación de sintaxis y estilo con `flake8`.
2.  **Unit Testing:** Ejecución de suite de pruebas con `pytest`.
3.  **Security Scan:** Revisión básica de vulnerabilidades.

---

## 📄 Documentación del Repositorio
* [Código de Conducta](CODE_OF_CONDUCT.md)
* [Guía de Despliegue](DEPLOYMENT.md)

**Autor:** Abrahan Vivas  
**Semestre:** 3er Semestre - DevOps Academics