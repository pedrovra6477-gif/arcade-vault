# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Idioma

Responde siempre en español.

## Proyecto

Arcade Vault: una plataforma de juegos en línea donde los jugadores compiten por la mayor cantidad de puntos. El proyecto sigue Spec Driven Design (flujo `/spec` y `/spec-impl`, de las skills `Klerith/fernando-skills`; ver README.md). Actualmente el código es el scaffold de Create Next App (`app/` solo contiene el layout y la página por defecto), por lo que todavía no existe arquitectura de juegos ni de puntuaciones.

## Skill
Usa siempre /frontend-desing para diseñar la interfaz del usuario

No hay un test runner configurado.

## Advertencia sobre la versión de Next.js

Next 16.4.6 / React 19.3 con cambios incompatibles respecto a lo que suele conocerse (ver AGENTS.md). Antes de escribir código de Next.js, lee la guía correspondiente en `node_modules/next/dist/docs/` (`01-app`, `02-pages`, `03-architecture`, `04-community`; empieza por `index.md`) y atiende los avisos de deprecación.

## Notas de configuración

- Solo App Router (`app/`). El alias de ruta `@/*` apunta a la raíz del repositorio.
- `next.config.ts` habilita `cacheComponents`, `partialPrefetching` y `experimental.agentFeedback`. `cacheComponents` cambia la semántica de caché y de renderizado dinámico, así que revisa la documentación antes de usar data fetching, `cookies()`/`headers()` o la configuración de segmentos de ruta.
- Tailwind CSS v4 está conectado mediante Turbopack: `next.config.ts` tiene una regla en `turbopack.rules` que procesa los `*.css` con `@tailwindcss/turbopack`. Los estilos se configuran en `app/globals.css` con `@import "tailwindcss"` y tokens `@theme inline` (no hay `tailwind.config`).
- TypeScript está en modo `strict`.
