# Notas de trabajo — Revisión del portafolio + nuevas tarjetas (jul 2026)

## Spec EXACTA de la tarjeta de referencia (portafolio-geraldine, index.html)

Grid: `display:grid;grid-template-columns:repeat(auto-fit,minmax(245px,1fr));gap:clamp(16px,2vw,22px)`

Tarjeta (article):
- `position:relative;overflow:hidden;background:var(--card);border:1px solid var(--line);border-radius:22px;cursor:pointer`
- hover: `transform:translateY(-7px);box-shadow:var(--shadow);border-color:var(--acc)`
- Imagen: `display:block;width:100%;aspect-ratio:4/3.3;object-fit:cover`
- Chip categoría sobre imagen: `position:absolute;left:12px;bottom:12px;padding:5px 11px;border-radius:999px;background:rgba(14,11,22,.5);backdrop-filter:blur(8px);color:#fff;font-size:11px;font-weight:700;letter-spacing:.04em`
- Footer: `display:flex;align-items:center;justify-content:space-between;gap:12px;padding:15px 17px`
  - h3: `font-size:15.5px;font-weight:800;letter-spacing:-0.01em`
  - sub: `margin:4px 0 0;font-size:12.5px;color:var(--text2)`
  - Botón flecha: círculo `width:34px;height:34px;border-radius:999px;border:1px solid var(--line);color:accInk;background:accSoft` con svg flecha `M5 12h14M13 6l6 6-6 6` (14x14)

Diferencias vs. tarjetas actuales del portafolio Richard:
- Actual: minmax(320px,1fr), aspect 16/10, título 19px, padding 22-24px, flecha 40px → tarjetas mucho más grandes (2 col). Referencia: minmax(245px), 4/3.3, compacta (3-4 col).

## Imperfecciones detectadas en la página actual

1. **Dos tipos de tarjeta**: rica (Cocina: cover+galería+modal completo) vs placeholder (desc + franja rayada + image-slot en modal). Hay que unificar al tipo 1.
2. **Tamaño de tarjeta** no corresponde al ejemplo (ver spec arriba).
3. **Zoom hover muerto**: la img de cover tiene `transition:transform .6s` pero ninguna regla la escala en hover.
4. **Alturas desiguales**: `sub: subtitle || desc` — los placeholders usan desc larga → footers de distinta altura.
5. **`modalSlotId = 'proj-'+idx`**: ids de image-slot por índice; si cambia el orden se desasocian las imágenes soltadas (desaparecerá al eliminar placeholders).
6. **LinkedIn**: tarjeta de contacto apunta a `https://www.linkedin.com/` genérico.
7. **Texto sección proyectos**: "Material visual en preparación" — actualizar cuando haya proyectos reales.
8. **360 en Drive**: PNGs de ~23MB → hay que convertir/comprimir a JPG antes de usarlas en el visor.
9. Imagen del modal fija a 54vh con object-fit:cover (recorta renders anchos) — aceptable, lightbox lo compensa.

## Inventario Google Drive (IDs clave)

Raíz `1GxnzewG-GPjnKj9o5HCuEFVnGJn4DdL9`:
- **01 Automatización y Datos** `1ehEl00M7O8vJDYxueuGgyBRX-0T8u2Xs`
  - Sistema Integral de Nómina `1HOiMt8NN76xI94yay76G3SK-ZkzhrdyN`: Informe doc `1G77uiwBQ_t8fMIn7hqvqTBT1Ly-b7qtwILBwsmDtWjw`; NOMINA ELECTRONICA V1.2.xlsm; Historial de Nóminas.xlsx; Consolidado Feb 2025.xlsx; "Copy of ARCHIVOS NOMINA INSTRUMATIC ox.xlsx" (nombre feo → renombrar). SIN capturas de pantalla.
  - Matriz de Entrenamientos `14YerFHmN6TYzdwF3u7rSaGusKLb2_nbL`: Informe doc `1mLHJ6WvlvgquMOmNCC3Kk7ZUp5qxSzmJciDQeuTT6ZA`; Playbook_Reporte_Capacitaciones_Barrick.md; MATRIZ CONTROL ENTRENAMIENTOS FINAL.xlsm; Base de fechas webcontrol.xlsx. SIN capturas.
  - Dashboards Ejecutivos `1bu55JA5CJYapWmqLq25sdwxRPErltJgq`: Informe doc `17PepRanXJX0U8dokPErGlmhqffi2Qa4PagV3wstd79k`; 1 xlsx. SIN capturas. (Contenido flaco)
  - Norplast `12QbLE95XZNGBAPRozUyhaABcamUcJyXC`: solo subcarpeta Facturas.
  - Pasantía Instrumatic `1BoWPyREzP22RKCXMBzWf_NxvjStimwTo`: sin explorar.
- **02 Diseño y Visualización** `1GTFIEHvECFJ4PXnR1uyEXRSa4k44t0eF`
  - Visualización Comercial `139B_PWv0_nQlKIDfzkyuUP6LY76rlPKf`
    - COCINA MELGORATTI - Colombia `1MMSX4XPK65WYg_nqNyO5Y7yUv-c-dMqS`: 1.png `1lIJWig_s1T9IAKDcT8HddtBQp6B-gwg6`, 2.png `1RtiG6UnD0GHhzVZJd4oJIRCVEbMpEl-2`, 3.png `1ZWhzVJ3Gxzm7K0swd4bn5Lxzgz4gzOWv`, 4.png `18PvOHqbHhjOinkcsPpkkwo9BGQaujgAG`; carpeta 360 `1BDet0uybCyfRNPDBaXqFx3uSpxltP9DI`; Vitrina - Melgoratti `1khONY5GrrSkOwPRbq8tgh0nLbnRPzStx`; Informe `13QBlo7XLhgXJEhHwVkkyPxqDsO9Rl0un1URI5NWZIiU`; reposteria.mp4 (309MB). = proyecto ya montado en la web (proyectos/cocina-*).
    - Proyectos `1SHSPmCMKbkgYO5q-AovplsiYU0zu9Q6j`: Rudy Castillo `1oEZJW5RslKOKcrxDTxNuh51olvYYBAv4`; INSTRUMATIC Pasantía `1pkkS00eIygOts7kIQwsuXwBVYubgvD7U` (sin explorar).
  - Visualización Residencial `1UhSunRtYqm53GKFGLxg943MAV7AgD0uc`
    - Apartamentos Josailyn y Josaniely `1EHtDTOGQ4GCsWr7g3gZY5T_oN0LV8xl5`: Informe `17yUP3i0HaIostmEgzXo-FXE_s6pVpUNNju_VKz-8RTM`; Exteriores: _26 `1s4o0hrWzMrQ3ItrmO8Oj9f5TmDmk7Alw`, _25 `15cgEZ54NbdjM51toU-8pxTVIrUtqiHK5`, _24 `1tohGZGf_KyUByaO8KthcYjYuitmemAas`, _23 `1n8wCpgdoeCPk0w8NTxoC5YiUO9jRajn3`, _22 `1XfozXY8R7pdJrUze96WM6NxnYhrcCURI`, _21 `1WGtJ2NIBzIFlPtNpsKBuLUYSaCVsV9B6`; Render Interior 1 `1FpnButZN3zSNLiUm4VnpIOIiPkxwPqHV`, Render Interior 2 `19XS9TPJCmA39uxeQqT5I7yUcAxYu3xeq`; Interior Josailyn_13.5 `1ll0HhDhcjQO0j0WJVPHXt3jg_arrswjC`, _14 `1AyIDYa6OC5iSivFCje_7Ra2rVuMfIO2L`, _15 `1ZynPQn49LacdCg4LfQMaTFONAmquCzGK`, _16 `14orD_39uUWxtNNZGufOA-JdT8KgFdvjc`, _17 `1yiYOYUVQ7cvJP-N7XiwsC8TmeeJxxzod`, _18 `1besCqwYrGwL2Gt7Gk2eWcqdmfIaxLbhF`, _19 `15WEGBSYWMCUY_d5XGWDlUBQ-2yw-F5Ta`, _20 `18n-FKULDS-5bqYRF6snMYLSAxch0oZAn`; Muestra Acabados.jpg `1VxyAxSa2SAgauMIGKUyZ3E0FLZ1F9ecS`; render fhd.jpg `1HKneLGCk-tfcasW01mxzg8E1b02PmjGD` (+ duplicado _lumion `17p9LObLVSRtS2l6l9zjEr1A3AqeYZgVu`); 360: `1c1MASZN_k6TjBeK7FSwIyeE22bpgr4eo` (360), `1oex87sDItG_m_LW-CYA_p_34Fnz39fhU` (360 2), `1QKRZuAV6FrTpNt9Vtzd6RSzA6_G36UWJ` (3.6), `1WCWhIRyrXIreuTwPJFloTSUgzi2g6qxE` (4.6), `1pcEi3Yc1ezsHuUosCudM3-XGB6yUiKe8` (5) — PNGs 22-25MB c/u; Render Final.mp4 (215MB).
    - Proyectos Braulio Santana `1SbdMroAyMfQki6diRxclyNQFUPUNdpQR`: Remodelación Casa `1IutteBWF0bc8KjzA23hHFqM_A2vqDjXB`, Concepto Casa `1gHX0hgcd1-jmXCEzVnoT09ooNBAWmq3a`, Casa Madre `18w4cS0Y0oHa3ODKCiLhjIb0x390g_rHn`, Concepto Apartamentos `1kTApflfUoGbiwh3K8NrIdOXUahumq5nm` (sin explorar).
  - Identidad Visual `119jbCb4Ynf7ynK3EjcCEDpjqdbm_u13P`: Blue Courier `1hnm6fYuPZoI2TfW27HAy83GhWBBjidMT`; Gradient Studio `1B_j_Geblx5kzn-7Ap0B2E3_ZDmdtwiWW`; sueltos: logos varios (Sakura Coffee, Norplast artboards, Plásticos Unidos, Level Rated, gaming) → desordenado, mover a subcarpetas.
- **Documentos** `1NuADGqrC26uUlK_shW59RCyE_q1ryo7l`, **Icons** `1YTDm2IQFlfPZs9tUvI6ktFC4Y_e4WzB9`.

## En el proyecto (uploads/) — posible material para automatización
- ~30 pasted-*.png (capturas pegadas en conversaciones previas — pueden ser capturas de los sistemas Excel)
- 4 videos 20260708-*.mp4 (posibles grabaciones de pantalla de los sistemas)

## Selección propuesta (adaptada al CV: automatización + datos + 3D)
1. Cocina Comercial Melgoratti (ya montada — corregir categoría: es Comercial, carpeta "Visualización Comercial")
2. Apartamentos Josailyn y Josaniely — Residencial · 3D (renders + 360 + informe)
3. Sistema Integral de Nómina — Automatización · VBA (informe ✓, faltan capturas)
4. Matriz de Entrenamientos — BI (informe ✓, faltan capturas)
5. (opcional) Dashboards Ejecutivos — flaco; ¿fusionar o esperar material?
6. (opcional) Identidad Visual — poco documentado
