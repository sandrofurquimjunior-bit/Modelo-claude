---
name: "escolha-de-modelo"
description: Recomenda qual modelo do Claude usar (Haiku, Sonnet, Opus ou Fable), com qual nível de Esforço e se o Pensamento deve ficar ligado, para uma tarefa específica, sempre com justificativa curta. Use esta skill sempre que o colaborador perguntar "qual modelo usar?", "qual esforço?", "preciso do Opus?", "vale usar o Fable?", "estou gastando muito limite", "por que a resposta veio rasa?", ou descrever uma tarefa e quiser saber a melhor configuração antes de começar, mesmo que não use a palavra "modelo".
---

# Escolha de Modelo e Esforço

## O que esta skill faz

Recomenda a configuração ideal para uma tarefa: **modelo + esforço + pensamento**.

Ela **não troca** o modelo sozinha. Quem ajusta é o usuário, no seletor que fica ao lado da caixa de mensagem (onde aparece o nome do modelo). Nesta etapa, não execute a tarefa em si; só recomende. Se a pessoa pedir, siga com a tarefa depois.

## Os três controles são independentes — e nem todo modelo tem os três

| Controle | Opções | O que muda |
|---|---|---|
| **Modelo** | Haiku, Sonnet, Opus, Fable | A capacidade de raciocínio disponível |
| **Esforço** | Baixo, Médio (padrão do modelo), Alto, xhigh (extra alto), Máx | Quanto processamento o modelo gasta. Mais esforço = resposta mais completa, porém mais lenta e consome o limite mais rápido. **Haiku não tem esse seletor** |
| **Pensamento** | Ligado / desligado (quando disponível) | O modelo raciocina antes de responder. Útil para tarefas com várias etapas ou lógica |

**Atenção ao Pensamento:** em **Opus 5.5, Fable 5.1 e Opus 5** o pensamento fica **sempre ligado** — não existe opção de desligar (nem no app, nem na API). Só é opcional em Sonnet, Fable 5, Haiku e versões mais antigas (4.6/4.7). **Nunca recomende "Pensamento desligado" para Opus 5.5, Opus 5 ou Fable 5.1.**

Recomende sempre os controles que existem para aquele modelo — não invente um toggle que ele não tem.

## Como decidir

Percorra as perguntas **na ordem** e pare na primeira que se aplicar:

1. **A tarefa é simples e curta?** Pergunta factual, correção gramatical, formatação, resumo curto, triagem de e-mails, reescrever uma mensagem curta.
   → **Haiku** (não tem seletor de esforço). Pensamento desligado, se a interface oferecer essa opção para o Haiku.

2. **É coding complexo ou uma tarefa agêntica de longa duração** (refatoração grande, agente rodando várias etapas sem supervisão constante)?
   → **Opus · xhigh** — pensamento sempre ligado.

3. **Um erro teria impacto alto e a correção é crítica** (valores financeiros, contratos, documentos para cliente externo, material para diretoria, dados que alimentam sistemas ou relatórios oficiais)?
   → **Opus · Alto** (ou **Máx** se o caso for excepcionalmente crítico) — pensamento sempre ligado, e **a revisão humana é obrigatória**.

4. **A tarefa é complexa** (várias etapas, documentos longos, planilhas grandes, cruzamento de várias fontes, arquitetura de solução), sem se encaixar nos casos acima?
   → **Opus · Médio** (padrão do modelo) — suba para Alto ou xhigh se a resposta vier rasa.

5. **É trabalho excepcionalmente difícil ou aberto** — pesquisa profunda, prototipação pesada, tarefa agêntica muito prolongada — e o ganho justifica o custo em créditos?
   → **Fable**, respeitando as regras de créditos abaixo. **Prefira Opus por padrão**: ele entrega nível Fable 5.1 na maioria das tarefas por cerca de 40% menos custo e sem precisar de créditos extras. Reserve o Fable para quando o Opus já foi testado e ficou comprovadamente aquém, ou quando a natureza da tarefa (pesquisa profunda, agente muito longo) já indicar isso de saída.

6. **Nenhuma das anteriores** (escrita, documentos, e-mails elaborados, análises do dia a dia, brainstorm, planejamento).
   → **Sonnet · Médio** (recomendação padrão). Pensamento ligado se houver raciocínio em etapas — nesse modelo dá pra desligar.

Se a descrição da tarefa for ambígua, faça **uma** pergunta curta antes de recomendar.

## Regras

- **Comece pelo mais leve que resolve.** Se a resposta vier rasa ou errada, primeiro aumente o esforço no mesmo modelo; se persistir, suba um modelo. É uma heurística, não uma regra fixa.
- **Na dúvida entre dois níveis, recomende o menor** e diga claramente em que situação subir.
- **Nunca recomende "pensamento desligado" para Opus 5.5, Opus 5 ou Fable 5.1** — não existe essa opção nesses modelos.
- **Fable tem salvaguardas adicionais** em áreas sensíveis (biologia, cibersegurança, P&D de IA) — nessas áreas seu comportamento pode ser mais restritivo. Não presuma que Fable é a melhor escolha só por ser um modelo mais "poderoso".
- **Créditos do Fable dependem do tipo de assento**: em assento Standard (Team/Pro), o Fable roda em créditos de uso desde a primeira mensagem; em assento Premium (Team/Max), fica incluso no limite semanal até 50% do consumo, depois exige créditos ou troca de modelo.
- **Mythos** é de acesso restrito. Não recomende.
- **Versões anteriores** (menu "Mais modelos"): só recomende quando a pessoa já tem um processo ou prompt validado em uma versão específica e quer resultados consistentes. Caso contrário, use a versão mais recente de cada família.
- O modelo escolhido **não muda** as regras de confidencialidade da organização. Dados sensíveis seguem a política de uso de IA em qualquer modelo.
- Não invente comparações de desempenho entre modelos. Se a pessoa perguntar algo que exige testar, diga que o jeito certo é testar a mesma tarefa nas duas configurações.

## Formato da resposta

Responda curto, neste formato:

**Modelo:** …
**Esforço:** … (omitir se o modelo não tiver esse seletor, como o Haiku)
**Pensamento:** ligado / desligado / sempre ligado (sem opção nesse modelo)
**Por quê:** uma frase
**Suba para … se:** uma frase

Não acrescente explicações longas, a menos que a pessoa peça.

## Referências

- `references/modelos.md`: famílias, versões atuais, custo, disponibilidade de esforço/pensamento por modelo e analogias para explicar. Leia quando a pessoa perguntar sobre versões, créditos ou diferenças entre modelos.
- `references/exemplos.md`: tarefas reais por área já classificadas. Leia quando precisar calibrar uma recomendação.
