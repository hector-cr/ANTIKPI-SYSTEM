# Esquema HU-001 — Atributos, Colecciones y Clases

## 1) Colecciones Firestore
### `reportSchedules/{scheduleId}`
```json
{
  "name": "Reporte KPIs Ventas",
  "ownerUid": "UID",
  "active": true,
  "frequency": "DAILY|WEEKLY|MONTHLY",
  "timeOfDay": "09:00",
  "dayOfWeek": 1,
  "dayOfMonth": 1,
  "timezone": "America/Mexico_City",
  "kpiParams": { "area": "ventas", "windowDays": 7 },
  "createdAt": "<serverTimestamp>",
  "lastRunKey": null
}
```

### "informe Ejecuciones"
```json
{
  "ownerUid": "UID",
  "scheduleId": "ID",
  "startedAt": "<serverTimestamp>",
  "finishedAt": "<serverTimestamp>",
  "status": "SUCCESS|FAILED",
  "message": "Detalle",
  "kpiSnapshot": {},
  "pdfPath": "reports/UID/SCHEDULE/2025-09-23T09-00-00.pdf",
  "pdfUrl": "https://...getDownloadURL...",
  "trigger": "SCHEDULED|MANUAL",
  "runKey": "SCHEDULEID:2025-09-23T09:00"
}
```

## 2) Atributos
```ts
export type Frequency = "DAILY" | "WEEKLY" | "MONTHLY";

export interface ReportSchedule {
  id: string;
  name: string;
  ownerUid: string;
  active: boolean;
  frequency: Frequency;
  timeOfDay: string;      // "HH:mm"
  dayOfWeek?: number;     // 1..7 si WEEKLY
  dayOfMonth?: number;    // 1..28 si MONTHLY
  timezone: string;       // "America/Mexico_City"
  kpiParams: Record<string, any>;
  createdAt: Date;
  lastRunKey?: string | null;
}

export interface ReportExecution {
  id: string;
  ownerUid: string;
  scheduleId: string;
  startedAt: Date;
  finishedAt?: Date;
  status: "SUCCESS" | "FAILED";
  message?: string;
  kpiSnapshot?: any;
  pdfPath?: string;
  pdfUrl?: string;
  trigger: "SCHEDULED" | "MANUAL";
  runKey: string;
}
```
