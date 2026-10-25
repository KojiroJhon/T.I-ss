# Meu Assistente TI

Organizador de tarefas para estagiários de TI: cadastro, prioridades, prazos, resumo diário e orientações do tipo "Como resolver?".

## Como rodar

```bash
npm run setup      # instala dependências e cria o banco SQLite (prisma/dev.db)
npm run dev        # http://localhost:3000
```

Antes, confira o arquivo `.env` (há um modelo em `.env.example`).

## Verificação

```bash
npm run typecheck
npm test
npm run build
```

## IA (opcional)

Defina `GEMINI_API_KEY` no `.env` (gratuita, criada em https://aistudio.google.com/apikey; somente no servidor) e reinicie. Também há suporte a `ANTHROPIC_API_KEY` (paga), usada só se a do Gemini estiver vazia. Com a IA ativa:
- foto da lista de tarefas (JPG/PNG/WebP, até 5 MB) e texto livre viram tarefas para você revisar antes de salvar;
- "Como resolver?" gera passos sob medida, sempre com orientação de quando procurar o supervisor.

Sem a chave, tudo continua funcionando: cadastro manual (uma tarefa por linha no texto livre) e guias básicos de Windows, hardware e rede.

## Estrutura

- `src/app/api/*` rotas de tarefas, IA e ajuda (validação com zod)
- `src/lib/*` regras puras (resumo, guias, validação) e cliente de IA (servidor)
- `src/components/*` interface
- `tests/*` testes com dados fictícios
