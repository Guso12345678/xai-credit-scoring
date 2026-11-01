# Esqueleto del informe (máx. 8 páginas, sin contar referencias)

Cada figura, con un pie que diga **qué debe concluir el lector**. Las cifras salen de `reports/results.json`; las figuras, de `reports/figures/`.
**Rellena con tu análisis en tus palabras; no pegues salidas del notebook sin interpretarlas.**

**Presupuesto orientativo** (contrasta los pesos con la tabla de la rúbrica del PDF): Intro 1 pág. (1.5 pts problema/dataset) · Data & Methods 1.5 (1 pt modelos/evaluación) · Results 2 (2.5 pts XAI) · Actions & Insights 2 (2 pts) · Discussion 1 (2.5 pts crítica) · presentación/repo (0.5 pts).

---
## Título · autor · fecha

## 1. Introduction (~1 pág.)
- Problema: predecir el impago de tarjeta a 1 mes; por qué hace falta explicar (analista de riesgos, gestor, solicitante, regulador).
- Contexto regulatorio (2–4 frases, con cita verificada): crédito = alto riesgo en el AI Act (Anexo III 5(b)); RGPD art. 22 y sentencia SCHUFA C-634/21; contrafactuales (Wachter et al., 2018). *Verifica fechas de aplicación en fuente oficial.*
- Objetivos (3 viñetas): qué criterios pesan · ¿son fiables las explicaciones? · qué acciones se derivan.
- Técnicas XAI usadas y por qué (global, local, evaluación).

## 2. Data and Methods (~1.5 págs.)
- 2.1 Dataset: fuente, n=30 000, 23 variables, tasa de impago (~22 %), limpieza (EDUCATION/MARRIAGE, duplicados). **SEX excluida de las entradas**, usada solo en auditoría. Limitaciones (Taiwán 2005, corte transversal). *Fig. 01_eda.*
- 2.2 Particiones estratificadas 60/20/20; test usado una sola vez.
- 2.3 Modelos: dummy, regresión logística, árbol (prof. 4), XGBoost (early stopping + búsqueda aleatoria). Métricas: ROC-AUC, PR-AUC, Brier, F1/precisión/recall al umbral de validación; IC bootstrap.
- 2.4 XAI: TreeSHAP (log-odds), permutation importance, gain, PDP/ICE, LIME, DiCE (acciones permitidas). Protocolo de evaluación de explicaciones (§5 del notebook).

## 3. Results (~2 págs.)
- 3.1 Rendimiento y sobreajuste: tabla `model_comparison`; gap train/val/test; CV 5-fold; calibración. *Fig. 02_model_eval.* ¿El XGBoost mejora de verdad a la logística?
- 3.2 Global: *Fig. 03_shap_beeswarm / 03_shap_bar*, dependencias (04), PDP/ICE (05); acuerdo entre métodos (`global_method_agreement`). Qué criterios dominan y por qué.
- 3.3 Local: 4 casos (TP, FN, FP, borderline) con waterfalls (06_*), SHAP vs LIME; contrafactuales DiCE y tasa de recurso factible (`recourse_feasibility`).
- 3.4 ¿Son fiables las explicaciones? Aleatorización de etiquetas y de parámetros, ROAR, permutar top-k, deletion, estabilidad LIME y SHAP-bootstrap (07, 08, 09). Tabla resumen: test → resultado → veredicto.

## 4. Actions and Insights (~2 págs.) — 4.1, 4.2 y 4.3 del PDF, cada una con métricas ANTES/DESPUÉS
- 4.1 Mejora del modelo guiada por XAI: variantes A–D; tabla con AUC val/test + IC y ΔAUC pareado; SHAP antes/después (10). **Si la mejora no es significativa, dilo y explica qué aprendes.**
- 4.2 Insights de negocio: deciles de riesgo (predicho vs observado), política por coste (FN:FP = 2/5/10, *supuestos*), SHAP por segmento. Recomendaciones concretas y qué monitorizar.
- 4.3 Equidad y robustez: auditoría por SEX/AGE/EDUCATION (paridad demográfica, equalized odds, TPR/FPR), SHAP por grupo, proxy AUC, ablación sin sensibles, mitigación ThresholdOptimizer (antes/después).

## 5. Discussion (~1 pág.) — la crítica pesa 2.5 pts
- Qué explicaciones resistieron los tests y cuáles no (inestabilidad de LIME, correlación entre BILL_AMT en SHAP, límites de la permutación con variables correlacionadas, aleatorización de parámetros en árboles que conserva la estructura).
- Riesgos de sobreinterpretar: SHAP ≠ causalidad; contrafactuales con acciones poco realistas (historial pasado inmutable); ataques (Slack et al., 2020).
- Validez externa: datos 2005/Taiwán; costes supuestos; partición aleatoria vs temporal.
- Trabajo futuro y conclusión (3–4 líneas).

## Referencias — solo las citadas (ver `docs/REFERENCES.md`)

## Apéndice: enlace al repo, comando de reproducción, versiones, declaración de uso de herramientas de IA (confirma si cuenta en las 8 págs.).

---
## Checklist final
- [ ] Cada punto del PDF (1–6) tiene apartado localizable.
- [ ] ≥ 3 técnicas XAI: global, local y evaluación.
- [ ] Modelo no sobreajustado: splits, gap, CV, IC; métricas adecuadas al desbalanceo.
- [ ] 4.1, 4.2, 4.3 con números antes/después.
- [ ] Crítica: limitaciones y fallos de las explicaciones, no solo éxitos.
- [ ] Repo: estructura, `requirements.txt`, README, notebook ejecutable de arriba abajo, semilla fija.
- [ ] Código/ideas externas citados; análisis en tus palabras; entiendes cada gráfico.
- [ ] ≤ 8 páginas.
