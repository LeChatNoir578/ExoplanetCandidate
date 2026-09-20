# 📑 Reporte de Análisis Astrofísico: Identificación y Filtrado de Exoplanetas Candidatos en el Catálogo TESS

**Autor:** Aaron Romo  
**Área:** Ciencia de Datos / Análisis Astrofísico  
**Herramientas:** Python, Pandas, Matplotlib, Seaborn, Astroquery (MAST / NASA API)  

---

## 1. Resumen del Proyecto

Este estudio aplicó un pipeline de filtrado y caracterización de datos sobre **4,404 candidatos a exoplanetas** (*TESS Objects of Interest* - TOI) procesados por la misión TESS de la NASA. 

El objetivo principal fue aislar candidatos de alto valor astrofísico en dos categorías clave:
1. **Planetas rocosos en Zona Habitable** (temperaturas aptas para agua líquida).
2. **Candidatos de Período Ultra-Corto (USP)** para estudios de firmas térmicas o tecnofirmas (SETI).

---

## 2. Metodología de Filtrado de Datos

El conjunto de datos original se sometió a las siguientes restricciones físicas y termodinámicas:

1. **Estimación del Radio Planetario ($R_p$):** Cálculo derivado de la profundidad de tránsito y el radio de la estrella anfitriona.
2. **Temperatura de Equilibrio ($T_{\text{eq}}$):** Estimación mediante la ley de Stefan-Boltzmann asumiendo albedo planetario moderado.
3. **Criterio de Habitabilidad:** Rango de temperatura de $-93\text{ °C}$ a $+37\text{ °C}$, seleccionando únicamente objetos rocosos puros ($R_p < 1.8\,R_\oplus$, por debajo del *Fulton Gap*).

---

## 3. Resultados Principales

De la población total analizada:
* **76 candidatos** se ubicaron dentro de los márgenes de temperatura de la Zona Habitable.
* **5 candidatos** cumplieron de manera estricta el criterio de ser **rocosos puros** ($R_p < 1.8\,R_\oplus$).
* **27 candidatos** se identificaron en la categoría USP (Período $< 1\text{ día}$).

---

## 4. Fichas Técnicas de Objetivos Prioritarios

### 🏆 1. Top Candidato Habitable: TOI 789.02 (TIC 300710077)
* **Radio Planetario:** $1.33\ R_\oplus$ (Super-Tierra rocosa)
* **Período Orbital:** $12.97\text{ días}$
* **Distancia Orbital:** $0.108\text{ UA}$ (~16.16 millones de km)
* **Temperatura de Equilibrio:** $+10.6\text{ °C}$ (Entorno templado)
* **Estrella Anfitriona:** Enana M ($T_{\text{eff}} = 3,461\text{ K}$, $R_* = 0.371\ R_\odot$)
* **Viabilidad Observacional:** Profundidad de tránsito de **$1.07\text{ ppt}$ ($0.107\%$)**. Altamente viable para seguimiento fotométrico desde telescopios terrestres de apertura moderada ($\ge 0.4\text{ m}$).

### 🛰️ 2. Top Candidato SETI / USP: TOI 1436.01 (TIC 154383539)
* **Radio Planetario:** $1.43\ R_\oplus$ (Cuerpo rocoso)
* **Período Orbital:** $0.8676\text{ días}$ ($20.8\text{ horas}$)
* **Temperatura de Equilibrio:** $+1,156.9\text{ °C}$
* **Magnitudes Estelares:** $V_{\text{mag}} = 12.01$, $T_{\text{mag}} = 11.09$, $G_{\text{mag}} = 11.66$
* **Viabilidad Observacional:** Excelente objetivo para espectroscopía de emisión térmica y eclipses secundarios mediante instrumentos del JWST (NIRSpec/MIRI).

---

## 5. Visualización Global y Discusión

Se generó un diagrama de dispersión en escala logarítmica ($Radio$ vs. $Período$) codificado por temperatura de equilibrio. En la visualización se destacan dos características demográficas clave:
1. **Fulton Gap ($1.8\,R_\oplus$):** La marcada escasez de planetas en esta frontera, la cual divide las Super-Tierras rocosas de los Sub-Neptunos con atmósferas volátiles.
2. **Gradiente Térmico:** La clara transición cromática donde la temperatura disminuye a medida que aumenta el período orbital.

---

## 6. Conclusiones

El pipeline implementado demostró ser eficaz para procesar grandes catálogos astronómicos públicos y extraer de forma automatizada objetivos prioritarios. Los candidatos **TOI 789.02** y **TOI 1436.01** representan los casos más prometedores del análisis para futuras campañas de caracterización o documentación técnica.
