# EmpireSite

Public marketing/institutional site for EmpireHub.

## Visão Geral

Site institucional público (landing, termos de uso, política de privacidade), fora do iframe do Discord e feito para ser indexável — perfil diferente do `EmpireClient` (SPA que nunca é indexada). Não tem auth nem economia própria, mas consome assets da `EmpireEngine` (ex.: preview de jogos/cosméticos na landing) — veja [`ARCHITECTURE.md`](../../../docs/project-planning-and-instructions/ARCHITECTURE.md). Construído com Astro (Islands Architecture, zero JS por padrão) — só os componentes pontualmente interativos viram ilha React.

## Estrutura

```
EmpireSite/
├── astro.config.mjs
├── public/
│   ├── favicon.ico
│   └── og-image.png
└── src/
    ├── pages/                        # cada arquivo = uma rota (roteamento por arquivo do Astro)
    │   ├── index.astro                 # landing page
    │   ├── privacy-policy/index.astro
    │   └── terms-of-service/index.astro
    ├── layouts/
    │   └── BaseLayout.astro            # layout compartilhado entre as páginas
    ├── components/
    │   ├── GamesShowcase.astro          # vitrine de jogos — consome assets da EmpireEngine
    │   └── LoginCta.tsx                 # única ilha React (componente interativo, ex.: CTA de login)
    └── styles/
        └── global.css
```

> Este README será ampliado com o fluxo real de consumo de assets da Engine assim que a codificação começar.
