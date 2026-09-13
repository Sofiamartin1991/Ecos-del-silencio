# 📄 Game Design Document (GDD) — Ecos del Silencio

**Proyecto:** Ecos del Silencio  
**Género:** Terror Psicológico Táctico / Supervivencia Cooperativa  
**Plataforma Target:** PC / Consolas  
**Clasificación:** ESRB Teen (+13) / PEGI 12  
**Lead Game Designer:** María Sofía Martín  
**Fecha:** Septiembre 2026  

---

## 1. Resumen Ejecutivo (High Concept)

*Ecos del Silencio* es un videojuego cooperativo táctico de terror psicológico donde una escuadra debe sobrevivir y completar objetivos de reconocimiento en entornos reales construidos a partir de datos satelitales. A diferencia del terror tradicional basado en sobresaltos (*jump scares*), el juego genera tensión mediante la escasez de recursos, la simulación física humana estricta y una **Inteligencia Artificial Adaptativa** que reacciona a los patrones de conducta y niveles de estrés del grupo.
### Concepto Artístico y Estético
* **Estilo "Silent Hill Real":** El mundo real capturado por satélite es progresivamente consumido por una atmósfera de niebla espesa, interferencia radial y una versión distorsionada/pesadillesca del entorno cotidiano. La ambientación apela al terror psicológico clásico (óxido, niebla, aislamiento y distorsión de la realidad) sobre calles y estructuras que el jugador reconoce en la vida real.
---

## 2. Pilares de Diseño (Core Design Pillars)

1. **Inmersión y Cartografía Real:** Los mapas del juego no son escenarios arbitrarios; son reconstrucciones procedurales basadas en datos cartográficos y de elevación reales.
2. **Terror Consecuencial (IA Adaptativa):** La amenaza no sigue rutas predecibles. Reacciona al ruido, a las transmisiones de radio, a las luces de las linternas y al grado de dispersión o pánico del equipo.
3. **Fisiología Humana Estricta:** El personaje no es un supersoldado. Sufre fatiga, hiperventilación, pérdida de pulso al apuntar en pánico y fallos mecánicos en el equipo electrónico por interferencias ambientales.
4. **Coordinación y Dependencia Mutua:** Ningún jugador puede sobrevivir solo. La comunicación y la estrategia de cobertura en escuadra son la única vía de extracción.

---

## 3. Mecánicas Principales (Core Mechanics)

### A. Sistema de Estrés y Percepción (Fisiología)
* **Estrés Dinámico:** Mirar directamente a la entidad, escuchar sonidos de origen desconocido o quedar aislado incrementa el ritmo cardíaco.
* **Efectos del Pánico:** A mayor estrés, la visión se estrecha (efecto túnel), el pulso al apuntar pierde precisión y la respiración se vuelve audible para las amenazas cercanas.
* **Gestión de Calma:** Uso de consumibles médicos o permanecer en la zona de cobertura visual de un compañero reduce gradualmente el pánico.

### B. Mapas Geoespaciales y Navegación
* **Uso de Datos Satelitales:** Generación de niveles a partir de coordenadas reales (topografía, densidad forestal, estructuras urbanas abandonadas).
* **Navegación Táctica:** No hay minimapa ni marcadores flotantes en la interfaz (HUD diegético). Los jugadores dependen de compases, mapas topográficos en papel y radiobalizas.

### C. IA Adaptativa del Entorno (Threat Engine)
* **Modelado de Comportamiento:** La entidad monitorea constantemente tres variables principales de la escuadra:
  * *Cohesión:* Grado de separación física entre jugadores.
  * *Emisión de Señal:* Uso de radios, linternas y detonaciones.
  * *Índice de Estrés:* Nivel acumulado de pánico del grupo.
* **Respuesta Dinámica:** Si el equipo se mueve en silencio y en grupo, la entidad se mantiene acechando en el perímetro. Si la escuadra entra en pánico o se separa, la entidad divided y caza a los miembros aislados.

---

## 4. Bucle de Jugabilidad (Core Loop) de 
[ Inserción en Zona Satelital ]
│
▼
[ Reconocimiento Táctico y Gestión de Silencio ]
│
▼
[ Alteración por IA Adaptativa (Eventos de Tensión) ]
│
▼
[ Resolución de Objetivos / Gestión del Pánico ]
│
▼
[ Extracción de la Escuadra ]


---

## 5. Arquitectura Técnica y Stack Sugerido

* **Motor de Juego:** Unity o Unreal Engine (Renderizado de vegetación y sombras en tiempo real).
* **Servicios Backend:** Convex / WebSockets para la sincronización del estado de los jugadores y la lógica del motor de IA en tiempo real.
* **Integración GIS:** APIs de servicios geográficos (Mapbox / OpenStreetMap API) para la importación de terreno satelital.
* **Audio:** Audio espacial 3D diegético (el sonido viaja por las estructuras físicas y depende del viento).

---

## 6. Hoja de Ruta del Desarrollo (Roadmap Hackatón)

* **Fase 1 (Día 1):** Documentación del GDD, arquitectura de datos en tiempo real y maquetación de la interfaz de escuadra.
* **Fase 2 (Día 2):** Integración de terreno base con malla de elevación satelital y controladores de movimiento humano estricto.
* **Fase 3 (Día 3):** Implementación del prototipo de la IA Adaptativa de entorno y testeo de eventos de pánico cooperativo.
