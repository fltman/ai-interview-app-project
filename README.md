# AI Interview App

[![Support me on Patreon](https://img.shields.io/badge/Patreon-Support%20my%20work-FF424D?style=flat&logo=patreon&logoColor=white)](https://www.patreon.com/AndersBjarby)

En Claude Code-baserad projektmall (blueprint) för att bygga en mobilanpassad webbapp som genomför röstbaserade intervjuer via OpenAI Realtime API och genererar dokument utifrån svaren. Repot innehåller specifikation, subagenter, slash commands och dokumentation som driver bygget — själva källkoden byggs upp via kommandona.

## Tänkt funktionalitet

1. **Inställningssida** — API-nyckel, röstval, systemprompt, intervjufrågor, slutmall och språk
2. **Intervjusida** — röstbaserad intervju via OpenAI Realtime API (WebRTC)
3. **Dokumentgenerering** — skapar dokument enligt mall, med möjlighet till översättning
4. **Export** — ladda ner eller dela via mobilens Web Share API

All logik körs i klienten (LocalStorage/IndexedDB) — ingen backend krävs, och API-nyckeln lämnar aldrig enheten utom till OpenAI.

## Vad ingår i repot

- `CLAUDE.md` — projektöversikt och riktlinjer för Claude Code
- `.claude/agents/` — subagenter (realtime-api, intervjulogik, UI, lagring, dokumentgenerering, test/QA)
- `.claude/commands/` — slash commands för setup och inkrementell implementation
- `docs/` — arkitektur, kom-igång och anteckningar om OpenAI Realtime API
- `package.json.template` — mall för det Vite/React-projekt som genereras

## Kom igång

Öppna projektet i Claude Code och kör kommandona i ordning:

```text
/project:setup                 # sätter upp Vite, React, TypeScript, Tailwind och beroenden
/project:implement-settings    # inställningssidan
/project:implement-realtime    # OpenAI Realtime API
/project:implement-interview   # intervjulogik
/project:implement-document    # dokumentgenerering
/project:test                  # tester
```

När projektet är scaffoldat används de vanliga npm-skripten (`npm run dev`, `npm run build`, `npm run lint`, `npm run typecheck`, `npm test`).

## Teknik

Avsedd stack: React + TypeScript + Vite + Tailwind CSS, OpenAI Realtime API (WebRTC), LocalStorage/IndexedDB. Repot självt är en Claude Code-mall (Markdown: CLAUDE.md, subagenter och slash commands).
