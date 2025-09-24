# Sistema Anti KPI — HU-001 (Vanilla JS + Firestore + Hosting)

**Actividad evaluada:** definición de colecciones, atributos y clases, y proyecto subido a GitHub.

## Historia de Usuario (HU-001)
Como administrador quiero generar reportes automáticos en PDF para entregar resultados con mayor eficacia a gerencia.

### Criterios cubiertos
- Programable (diario/semanal/mensual + hora)
- PDF con sello de fecha/hora
- Guardado en Storage y enlace seguro (getDownloadURL)
- Log de ejecución en Firestore

## Colecciones (Firestore)
- `reportSchedules/{scheduleId}`
- `reportExecutions/{executionId}`

Consulta `docs/schema.md` para el detalle de atributos.

## Clases / Tipos
- `ReportSchedule`
- `ReportExecution`

Consulta `public/app.js` (JSDoc typedefs) y `docs/schema.md` (TypeScript).

## Cómo ejecutar
1. Crear proyecto Firebase y pegar `firebaseConfig` en `public/app.js`.
2. `firebase login`
3. `firebase init` (hosting y firestore). Acepta usar `public/`.
4. `firebase deploy`

## Cómo subir a GitHub
```bash
git init
git branch -M main
git add .
git commit -m "HU-001: atributos, colecciones, clases y base de proyecto"
gh repo create anti-kpi-hu001 --public --source=. --remote=origin --push
# Si no usas GitHub CLI:
# Crear repo manual en GitHub y luego:
# git remote add origin https://github.com/<usuario>/anti-kpi-hu001.git
# git push -u origin main
```