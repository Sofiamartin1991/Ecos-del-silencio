# 🏗️ Ecos del Silencio — Arquitectura del Sistema

Este documento describe la arquitectura técnica y el flujo de datos para **Ecos del Silencio**, un videojuego táctico de terror psicológico multijugador con integración de mapas geolocalizados e Inteligencia Artificial adaptativa.

---

## 📐 1. Diagrama de Flujo del Sistema

[ Cliente del Juego ]
│
├──► Mapbox / Satellite API ──► (Generación de Mapa & Entorno 3D)
│
├──► Convex Server Backend ──► (Sincronización Multijugador & Estado de Sala)
│
└──► Nebius AI Engine ───────► (Procesamiento de Estrés & Lógica de Entes)


---

## 🛰️ 2. Componentes Principales

### A. Cliente (Game Client)
* **Motor:** Unity / Unreal Engine (Renderizado 3D en 3ra persona con cámara fluida de 360°).
* **Filtros Post-Procesado:** Shaders de grano de película, niebla volumétrica y baja iluminación dinámica (Estética *Silent Hill / Resident Evil*).
* **Mapeo Satelital:** Consumo de APIs de geolocalización para convertir coordenadas GPS en entornos jugables en tiempo real.

### B. Backend Multijugador en Tiempo Real
* **Tecnología:** Convex / Node.js
* **Responsabilidad:**
  * Gestión de salas y matchmaking táctico.
  * Sincronización de posiciones de jugadores y estado del arsenal.
  * Gestión de inventario de consumibles y herramientas de contención.

### C. Motor de IA Adaptativa
* **Tecnología / Infraestructura:** Nebius AI Engine (APIs de baja latencia)
* **Función:**
  * Evaluación continua de parámetros de estrés del jugador (salud, munición restante, aislamiento en el mapa).
  * Modificación en tiempo real del *spawning*, comportamiento y patrones de acecho de las 3 categorías de entes (Espectros, Leyendas Urbanas y los 13 Fantasmas).

---

## 🔒 3. Seguridad & Licencia
* **Modelo de Licencia:** No License (All Rights Reserved). 
* Todo el código fuente, diseño conceptual y documentación técnica pertenecen exclusivamente a los autores del proyecto.
  
