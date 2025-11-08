# Módulo de Promociones (TELCO, 2015–2017)

🧩 Caso real adaptado para portafolio profesional. Rol: Product Manager Desarrollo (PO funcional).  
👥 Coordinación transversal con Marketing, Desarrollo, TI, CRM y Billing.

---

## 🎯 Objetivo

Habilitar promociones automáticas por evento (altas, cambios de plan, recargas, bolsas), con trazabilidad y menor time-to-market.  
MVP: módulo backend para otorgar **bolsas de datos** y **descuentos** con reglas configurables.

---

## ⚙️ Contexto

Antes: promociones configuradas manualmente, sin trazabilidad ni continuidad.  
Presión de campaña fija (portabilidad 2+ líneas) obligó a acelerar automatización.  
Se priorizó **la bolsa de 10 GB 4G** para altas nuevas y segmento híbrido, con ventana operativa de 1 año.

---

## 🔧 Enfoque y decisiones clave

- **Sin GUI inicial** (se incorporó en iteración posterior con training).
- **UAT simplificado**: pruebas acotadas en producción, por segmento y modalidad.
- **Feature flags** y scope congelado: enfoque en estabilidad operativa.
- **Workaround documentado**: para errores funcionales menores.

---

## 📦 Implementación

- Definición de reglas por evento y segmento (vigencias, condiciones, límites).
- Integraciones con BSCS iX, Siebel CRM, ALU ICC, Huawei UPCC (PCRF).
- Backlog funcional, criterios de aceptación y testing end-to-end.
- Catálogo versionado de promociones; control de cambios y checklist de liberación.
- Comunicación interna y plan de soporte post go-live.

---

## 📈 Resultados y métricas

| KPI                         | Línea base | Resultado | Notas                                     |
|----------------------------|------------|-----------|-------------------------------------------|
| **TTGL** (semanas)         | 6          | 3         | Go-live en fecha comprometida             |
| **TTV** (días a adopción)  | —          | ⟨N⟩       | Activación + comunicaciones efectivas     |
| Errores config / release   | 8          | 2         | Controlados vía workaround y checklist    |

- Time-to-market de nuevas promociones pasó de semanas a días.
- Mayor trazabilidad por segmento/evento → reducción de errores operativos.
- Adopción funcional temprana; confianza interna para siguientes campañas.

---

## 🚀 Go-live y soporte

- Despliegue controlado sin ceremonia formal.
- Validación funcional en producción: altas, cambios, beneficios aplicados.
- Monitoreo post-lanzamiento: 2 rondas diarias por 1 semana con N2 y canales.
- Coordinación con Atención, Reportería y Operaciones.

---

## 📚 Artefactos incluidos

📁 `/diagrams`  
- [`flujo-to-be.mmd`](./diagrams/flujo-to-be.mmd): flujo por segmento/modalidad.  
- [`contexto-sistemas.mmd`](./diagrams/contexto-sistemas.mmd): vista de sistemas (canales, CRM, orquestador, core).

📁 `/docs`  
- [`catalogo-reglas.md`](./docs/catalogo-reglas.md): reglas por segmento/modalidad.  
- [`criterios-aceptacion.md`](./docs/criterios-aceptacion.md): criterios de aceptación por caso.  
- [`kpis.md`](./docs/kpis.md): definición de TTGL/TTV y notas de medición.

📁 `/uat`  
- [`plan-uat.md`](./uat/plan-uat.md): plan de pruebas simplificadas en prod.  
- *(bitácora de hallazgos omitida en esta versión)*

📁 `/comms`  
- [`comunicado-lanzamiento.md`](./comms/comunicado-lanzamiento.md): anuncio interno.  
- [`checklist-go-no-go.md`](./comms/checklist-go-no-go.md): criterios de validación.

---

## 🧠 Aprendizajes

✅ Lo que funcionó:
- MVP simple con reglas claras.
- Monitoreo cercano y coordinación efectiva.

🔧 Mejoras futuras:
- Incluir PM técnico para handover evolutivo.
- Incorporar GUI de soporte desde iteración 1.
- Mayor alineación con proveedor de plataforma.

---

🛈 **Nota:** Este caso ha sido adaptado para fines de portafolio profesional. Se han omitido nombres comerciales, cifras sensibles y detalles internos, manteniendo fiel el enfoque funcional, decisiones clave y resultados alcanzados en contexto real.

---

## 🤝 Créditos

Equipos de Marketing, TI, CRM, Billing, Atención y Proveedores (ALU/Nokia, Huawei).  
Rol funcional: Product Owner (Product Manager Desarrollo).