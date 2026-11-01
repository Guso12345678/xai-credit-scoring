# Referencias

Los identificadores arXiv de esta lista se han comprobado contra el título del artículo. Cada entrada lleva un identificador (arXiv / DOI / URL oficial) para que puedas comprobarla en 1 minuto.
**Antes de entregar, abre cada enlace y copia el formato de cita que exija tu profesor** — no cites nada que no hayas
comprobado ni que no uses de verdad en el informe.

## Datos
- Yeh, I-C. & Lien, C-H. (2009). *The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients.* Expert Systems with Applications, 36(2), 2473–2480. — Dataset Taiwan. UCI: https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients
- Hofmann, H. (1994). *Statlog (German Credit Data).* UCI ML Repository, DOI 10.24432/C5NC77. https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data
- Grömping, U. (2019). *South German Credit Data: Correcting a Widely Used Data Set.* Reports in Mathematics, Physics and Chemistry 4/2019, Berliner Hochschule für Technik. UCI: https://archive.ics.uci.edu/dataset/573/south+german+credit+update
- FICO Explainable ML Challenge (HELOC): https://community.fico.com/s/explainable-machine-learning-challenge (formulario de acceso)

## Modelos y evaluación
- Chen, T. & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System.* KDD '16. arXiv:1603.02754
- Friedman, J. H. (2001). *Greedy function approximation: a gradient boosting machine.* Annals of Statistics, 29(5). (PDP)
- Goldstein, A., Kapelner, A., Bleich, J., Pitkin, E. (2015). *Peeking inside the black box: ICE plots.* J. Computational and Graphical Statistics, 24(1). arXiv:1309.6392

## Técnicas XAI
- Lundberg, S. M. & Lee, S.-I. (2017). *A Unified Approach to Interpreting Model Predictions.* NeurIPS 30. arXiv:1705.07874
- Lundberg, S. M. et al. (2020). *From local explanations to global understanding with explainable AI for trees.* Nature Machine Intelligence, 2, 56–67. (TreeSHAP)
- Chen, H., Janizek, J. D., Lundberg, S., Lee, S.-I. (2020). *True to the Model or True to the Data?* arXiv:2006.16234 (path-dependent vs interventional SHAP)
- Ribeiro, M. T., Singh, S., Guestrin, C. (2016). *"Why Should I Trust You?": Explaining the Predictions of Any Classifier.* KDD '16. arXiv:1602.04938 (LIME)
- Mothilal, R. K., Sharma, A., Tan, C. (2020). *Explaining Machine Learning Classifiers through Diverse Counterfactual Explanations.* FAT* '20. arXiv:1905.07697 (DiCE)
- Wachter, S., Mittelstadt, B., Russell, C. (2018). *Counterfactual Explanations without Opening the Black Box.* Harvard Journal of Law & Technology, 31(2). arXiv:1711.00399
- Ustun, B., Spangher, A., Liu, Y. (2019). *Actionable Recourse in Linear Classification.* FAT* '19. arXiv:1809.06514
- Breiman, L. (2001). *Random Forests.* Machine Learning, 45, 5–32. (permutation importance) · Fisher, A., Rudin, C., Dominici, F. (2019). *All Models are Wrong, but Many are Useful.* JMLR 20(177). arXiv:1801.01489

## Evaluación / crítica de las explicaciones
- Adebayo, J. et al. (2018). *Sanity Checks for Saliency Maps.* NeurIPS 31. arXiv:1810.03292
- Hooker, S., Erhan, D., Kindermans, P.-J., Kim, B. (2019). *A Benchmark for Interpretability Methods in Deep Neural Networks (ROAR).* NeurIPS 32. arXiv:1806.10758
- Alvarez-Melis, D. & Jaakkola, T. (2018). *On the Robustness of Interpretability Methods.* arXiv:1806.08049
- Slack, D. et al. (2020). *Fooling LIME and SHAP: Adversarial Attacks on Post hoc Explanation Methods.* AIES '20. arXiv:1911.02508
- Kumar, I. E. et al. (2020). *Problems with Shapley-value-based explanations as feature importance measures.* ICML 2020. arXiv:2002.11097
- Molnar, C. et al. (2020). *General Pitfalls of Model-Agnostic Interpretation Methods for Machine Learning Models.* arXiv:2007.04131 (2020 version titled *Pitfalls to Avoid when Interpreting Machine Learning Models*, ICML XXAI workshop)
- Rudin, C. (2019). *Stop explaining black box models for high stakes decisions and use interpretable models instead.* Nature Machine Intelligence, 1, 206–215. arXiv:1811.10154
- Molnar, C. *Interpretable Machine Learning* (libro online). https://christophm.github.io/interpretable-ml-book/

## Equidad
- Hardt, M., Price, E., Srebro, N. (2016). *Equality of Opportunity in Supervised Learning.* NeurIPS 29. arXiv:1610.02413
- Bird, S. et al. (2020). *Fairlearn: A toolkit for assessing and improving fairness in AI.* Microsoft Tech. Report MSR-TR-2020-32. https://fairlearn.org

## Crédito + XAI (para la introducción / discusión)
- Bücker, M., Szepannek, G., Gosiewska, A., Biecek, P. (2022). *Transparency, Auditability and eXplainability of Machine Learning Models in Credit Scoring.* J. Operational Research Society, 73(1). arXiv:2009.13384
- Bussmann, N., Giudici, P., Marinelli, D., Papenbrock, J. (2021). *Explainable Machine Learning in Credit Risk Management.* Computational Economics, 57, 203–216.

## Marco regulatorio (**verifica los textos oficiales; no los he podido abrir todos**)
- Reglamento (UE) 2024/1689 (AI Act): la evaluación de solvencia de personas físicas figura como sistema de alto riesgo (Anexo III, punto 5(b)). Fechas de aplicación: **comprueba en fuente oficial** (hay propuestas de retraso en curso). Búsqueda oficial: https://eur-lex.europa.eu/eli/reg/2024/1689/oj *(enlace no verificado desde mi entorno)*
- Reglamento (UE) 2016/679 (RGPD), art. 22 (decisiones individuales automatizadas) y considerando 71.
- TJUE, sentencia de 7-dic-2023, asunto C-634/21 (SCHUFA Holding): la generación de una puntuación crediticia puede constituir «decisión automatizada» del art. 22 RGPD cuando un tercero se apoya de forma determinante en ella.

## Software (cita si lo usas)
shap (Lundberg), lime (Ribeiro), dice-ml (Mothilal et al.), fairlearn, xgboost, scikit-learn (Pedregosa et al., 2011, JMLR 12), ucimlrepo.
