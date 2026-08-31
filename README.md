# Calculadora QTc Profesional

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://calculadoraqtc.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-v2.0-blue)](https://calculadoraqtc.github.io/)

Calculadora de QT corregido (QTc) profesional, open source, diseñada para uso clínico diario. Soporta 4 fórmulas, interpretación por edad y sexo, entrada en cuadraditos (como se mide en el ECG) o segundos, y por intervalo RR o frecuencia cardíaca. Con modo oscuro para guardia nocturna.

**Demo:** https://calculadoraqtc.github.io/

<img src="/og-image.png" alt="Calculadora QTc Preview" width="100%">

## ✨ Features v2.0

- **4 fórmulas:** Bazett (default), Fridericia, Framingham y Hodges
- **6 grupos con valores de referencia:** Lactantes <6m, Niños 6m-12a, Adolescentes varón/mujer, Adultos hombre/mujer
- **Entrada flexible:**
  - QT y RR en **cuadraditos** (1 cuad chico = 0.04s) o segundos
  - RR o FC (20-300 lpm) → calcula RR automáticamente
- **Interpretación automática con colores:** Corto (azul), Normal (verde), En el límite (ámbar), Prolongado (rojo)
- **Desglose del cálculo:** Muestra fórmula y operación (ej: `0.36s / √0.84s = 0.393s`)
- **Tabla de referencia que resalta** el grupo seleccionado
- **Modo oscuro/claro** con toggle 🌙/☀️, guarda preferencia en localStorage y respeta `prefers-color-scheme`
- **100% client-side:** Sin backend, sin tracking, funciona offline
- **PWA-ready:** manifest.json + favicons + og-image para WhatsApp

## 📐 Fórmulas

| Fórmula | Ecuación | Cuándo usar |
|---|---|---|
| **Bazett** | `QTc = QT / √RR` | Uso general, comparabilidad histórica, pediatría |
| **Fridericia** | `QTc = QT / ∛RR` | FC >80 lpm, oncología, fármacos que suben FC |
| **Framingham** | `QTc = QT + 0.154·(1-RR)` | Amplio rango de FC, estudios poblacionales |
| **Hodges** | `QTc = QT + 1.75·(FC-60)` en ms | Bradicardia marcada o ejercicio |

RR en segundos, QT en segundos. Resultado en ms.

## 📊 Valores de referencia (ms) - AHA/ACCF/HRS

| Grupo | Corto | Normal | Límite | Prolongado |
|---|---|---|---|---|
| Lactantes <6m | <360 | 360–450 | 451–460 | >460 |
| Niños 6m–12a | <360 | 360–440 | 441–460 | >460 |
| Adolescentes varones | <340 | 340–450 | 451–460 | >460 |
| Adolescentes mujeres | <340 | 340–460 | 461–470 | >470 |
| Adultos hombres | <340 | 340–450 | 451–460 | >460 |
| Adultos mujeres | <340 | 340–460 | 461–470 | >470 |

## 🩺 ¿Cómo medir QT correctamente?

1. DII o V5, velocidad 25mm/s
2. Desde inicio del QRS hasta final de onda T (retorno a línea basal)
3. Promediar 3-5 latidos, excluir extrasístoles y onda U
4. En T bifásica/mellada, medir hasta final de la deflexión
5. 1 cuadradito chico = 1mm = 0.04s

> **Tip:** Si QTc está en límite, calculá con 2 fórmulas (ej: Bazett + Fridericia). Controlá K+, Mg2+, Ca2+ y fármacos (macrólidos, antipsicóticos, antiarrítmicos).

## 🚀 Deploy en GitHub Pages

1. Cloná o forkeá este repo `calculadoraqtc.github.io`
2. Subí a la raíz:
   - `index.html`
   - `qtc_icon_transparent.png`, `qtc_logo_transparent.png`, `og-image.png`
   - `favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png`, `favicon-192x192.png`, `favicon-512x512.png`, `apple-touch-icon.png`
   - `manifest.json`, `sitemap.xml`, `robots.txt`, `LICENSE`, `README.md`
3. GitHub Pages se publica automático en https://calculadoraqtc.github.io/
4. Verificá OG en https://www.opengraph.xyz/

No necesita build. Es HTML + Tailwind CDN + vanilla JS.

## 📚 Bibliografía

- Schwartz PJ et al. Guidelines for the interpretation of the neonatal QTc. JACC 2020.
- Rautaharju PM et al. AHA/ACCF/HRS Recommendations for the Standardization and Interpretation of the Electrocardiogram. JACC 2009.
- Bazett HC. An analysis of the time-relations of electrocardiograms. Heart 1920;7:353-370.
- Fridericia LS. Die Systolendauer im Elektrokardiogramm bei normalen Menschen und bei Herzkranken. Acta Med Scand 1920.

## ⚠️ Disclaimer

Herramienta de apoyo educativo. No sustituye el juicio clínico. Verificar siempre mediciones y contexto del paciente. No almacena datos de pacientes.

## 👨‍⚕️ Autor

**Miguel — Doctor en Medicina**
- Sitio: https://calculadoraqtc.github.io/
- GitHub: @calculadoraqtc

## 📄 Licencia

MIT License - ver [LICENSE](./LICENSE) para detalles. Uso libre para fines educativos y clínicos, con atribución.

---
Hecho con 💓 y ECG en Uruguay.
