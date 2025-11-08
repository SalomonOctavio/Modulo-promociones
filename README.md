# Módulo de Promociones (WOM, 2015–2017)

Rol y alcance Product Manager Desarrollo · transversal con MarketingDesarrollo, TI, CRMBilling.  
Sistemas implicados Ericsson BSCS iX, Oracle Siebel CRM, ALU 8610 ICC, Huawei UPCC (PCRF).

## Contexto
Impulsar campañas de promociones basadas en eventos (altas, cambios de plan, recargas, compras de bolsas), evitando configuraciones manuales dispersas y logrando trazabilidad entre canales.

## Contexto y disparador inicial
Promociones se ejecutaban de forma **manual**, sin descuentos recurrentes; el “enganche” venía por precios de equipos/portabilidad. Con campaña de portabilidad **2+ líneas** y presión de fechas, se gatilló la **automatización**. 

## Objetivo de negocio
Aumentar upsellretención y mejorar CX habilitando reglas de negocio que asignen promociones automáticas y medibles por segmentoevento.

## Alcance y restricciones
**MVP:** módulo para otorgar **bolsas** y **descuentos**; **caso base**: altas reciben **bolsa 4G de 10 GB**; soporte a prepago “híbrido”. Ventana dura: campaña 4G (~1 año). **Dependencias**: BSCS iX, ALU 8610 ICC, Huawei UPCC (PCRF). 

## Problema
- Promociones manuales y desalineadas entre sistemas.  
- Baja trazabilidad y time-to-market lento para nuevas campañas.  
- Riesgo de errores operativos en configuración y despliegue.

## HipótesisPropuesta
Diseñar un módulo orquestador de promociones orientado a eventos, con catálogo versionado de reglas y flujos de validaciónUAT E2E para salida segura a producción.

## Enfoque (decisiones clave)
- **Sin GUI** en 1ª etapa (se incorpora más tarde con capacitación).  
- **UAT simplificado**: pruebas directas en prod por alta de oferta y escenarios acotados.  
- **Regla simple** para acelerar: aplicar la bolsa a toda la base (menos ramificaciones).  
- **Scope pragmático**: reducir errores (no sanear todas las inconsistencias). 

## Enfoque y ejecución
- Definición de reglas por eventosegmento (condiciones, vigencias, límites).  
- Integraciones con BSCSCRMICCPCRF y mapeos de datos para gatillar beneficios.  
- Backlog y criterios de aceptación; planificación y UAT end-to-end (negocio + TI).  
- Catálogo de promociones con versionado y control de cambios.  
- Comunicaciones de lanzamiento y playbooks de soporte post–Go-Live.

## Resultado (KPIsOutcomes)
- Time-to-market nuevas promociones configurables en horasdías (antes, semanas). (estimado)  
- Calidad reducción de errores manuales y mayor trazabilidad por eventosegmento. (cualitativo)  
- Negocio tendencia positiva en upsellretención en campañas gatilladas por eventos. (cualitativo)
**TTGL** cumplido en fecha; **TTV** con adopción temprana y caída de errores (mitigados con el workaround). Efectos: **trazabilidad** de beneficios y **confianza** comercial por mayor previsibilidad. 

## Go-live y control
Despliegue **rápido** (sin ceremonia formal), **smoke mínimo**. Monitoreo post por Call Center y **N2** + rondas **2×/día** por una semana. **Workaround** documentado para errores detectados. 

## Estabilidad y soporte post
Monitoreo inicial, corrección temprana de incidencias y checklist de Go-Live; coordinación con Operaciones, Atención y Reportería para cierre de brechas.

## Aprendizajes
Repetir: **MVP simple** con reglas claras; **monitoreo cercano** post-lanzamiento.  
Mejorar: más alineación con proveedor IT; **PM dedicado** para handover; planificar **GUI soporte** desde la iteración 1. 

## Métricas (TTGL/TTV)
| KPI | Línea base | Resultado | Nota |
|---|---:|---:|---|
| **TTGL** (semanas) | 6 | 3 | Campaña en fecha |
| **TTV** (días a adopción) | n/a | ⟨N⟩ | Activación + comms |
| Errores config/release | 8 | 2 | Workaround + checklist |

**Artefactos incluidos**

📁 `/diagrams`  
- [`flujo-to-be.mmd`](./diagrams/flujo-to-be.mmd): flujo funcional por segmento y modalidad (B2C/B2B, Postpago/Híbrido).  
- [`contexto-sistemas.mmd`](./diagrams/contexto-sistemas.mmd): vista de integración entre canales, CRM, orquestador y sistemas core (PCRF, BSCS).

📁 `/docs`  
- [`catalogo-reglas.md`](./docs/catalogo-reglas.md): catálogo de reglas de promoción por segmento.  
- [`criterios-aceptacion.md`](./docs/criterios-aceptacion.md): criterios de aceptación por escenario funcional.  
- [`kpis.md`](./docs/kpis.md): definición de KPIs TTGL/TTV y placeholders.

📁 `/uat`  
- [`plan-uat.md`](./uat/plan-uat.md): plan de validación UAT por ventana de campaña.  
- [`bitacora-hallazgos.md`](./uat/bitacora-hallazgos.md): hallazgos funcionales en ambiente productivo.

📁 `/comms`  
- [`comunicado-lanzamiento.md`](./comms/comunicado-lanzamiento.md): anuncio de go-live y alcance funcional.  
- [`checklist-go-no-go.md`](./comms/checklist-go-no-go.md): criterios de validación previos a liberación.


## Créditos y roles
MarketingDesarrollo, TI (CRMBillingRed), Procesos, Atención; proveedores de plataforma (ALUNokia, Huawei).
