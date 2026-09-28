# Modelos disponíveis

> **Atualize este arquivo** sempre que o seletor de modelos mudar. A lógica do `SKILL.md` usa só as famílias, não os números de versão.
>
> Última verificação: 26/09/2026, contra a documentação oficial da Anthropic (support.claude.com e platform.claude.com). Confirme no seletor do Claude antes de citar números de versão — a Anthropic lança atualizações com frequência.

## Famílias

| Família | Perfil | Quando usar | Custo |
|---|---|---|---|
| **Haiku** | Rápido e leve | Tarefas simples, alto volume, respostas rápidas | Consome menos limite |
| **Sonnet** | Equilíbrio | Maior parte do trabalho do dia a dia (recomendação padrão) | Moderado |
| **Opus** | Alto desempenho | Tarefas complexas, raciocínio avançado, alto risco de erro, coding/agentes longos (xhigh) | Consome mais limite (ficou ~40% mais barato na versão 5.5 — ver nota abaixo) |
| **Fable** | Nível acima do Opus, com salvaguardas extras em biologia, cibersegurança e P&D de IA | Pesquisa profunda, trabalho aberto, tarefas agênticas muito prolongadas, quando o ganho justifica | **Pode exigir créditos de uso, dependendo do assento** (ver nota) |
| **Mythos** | Nível mais alto; mesmo modelo base do Fable, com salvaguardas diferentes | Acesso restrito a poucas organizações | Não disponível para uso geral |

## Esforço e Pensamento: o que cada modelo suporta (confirmado no Help Center)

| Modelo | Tem seletor de Esforço? | Pensamento pode ser desligado? |
|---|---|---|
| Haiku 4.5 | Não | Sim (toggle manual) |
| Sonnet 5 / Sonnet 4.6 | Sim (Baixo → Máx) | Sim |
| Opus 5.5 | Sim (Baixo → Máx) | Não — sempre ligado |
| Opus 5 | Sim (Baixo → Máx) | Não — sempre ligado (no app; na API dá pra desligar só até esforço Alto) |
| Opus 4.6 / 4.7 | Sim | Sim |
| Fable 5.1 | Sim (Baixo → Máx) | Não — sempre ligado |
| Fable 5 | Sim | Sim |

Os cinco níveis de esforço são: **Baixo, Médio, Alto, xhigh (extra alto), Máx**. Não existe nível "Extra" — o nome oficial é **xhigh**, pensado para coding e tarefas agênticas de longa duração; Máx é para o raciocínio mais profundo possível.

## Versões no seletor (verificar sempre no app — muda com frequência)

- **Lista principal (26/09/2026):** Opus 5.5, Fable 5.1, Opus 5, Sonnet 5, Fable 5, Haiku 4.5
- **Mais modelos:** Opus 4.8, Opus 4.7, Opus 4.6, Sonnet 4.6, Opus 3, e outras versões legadas

Número maior = versão mais recente, que em geral traz ganhos incrementais de qualidade. Versões antigas só fazem sentido para manter consistência com um processo já validado.

### Nota: Opus 5.5 (lançado 22/09/2026)

- O **Opus 5.5** passou a ser o modelo padrão do Claude.ai e do Claude Code para novos usuários, substituindo modelos anteriores como seleção inicial.
- A Anthropic reporta um custo por tarefa **cerca de 40% menor** que o Opus 5, com desempenho no nível do **Fable 5.1 na maioria dos trabalhos**.
- Isso reduz bastante os casos em que vale pagar por Fable — reserve o Fable para quando a tarefa exigir algo que o Opus 5.5 comprovadamente não entrega, ou para pesquisa profunda/trabalho aberto/agentes muito longos, onde a documentação já posiciona o Fable como a opção certa de saída.

### Nota: créditos do Fable por tipo de assento (confirmado no Help Center, artigo "Claude Fable models on your plan")

- **Assento Standard (Team) / plano Pro:** Fable roda em créditos de uso pré-pagos desde a primeira mensagem — não está incluso no limite semanal.
- **Assento Premium (Team) / plano Max:** Fable é parte do plano até 50% do limite semanal do usuário; depois disso, créditos de uso ou trocar de modelo.
- Isso vale igualmente para Fable 5 e Fable 5.1.

## Esforço

| Nível | Uso típico |
|---|---|
| Baixo | Respostas rápidas e simples |
| Médio (padrão) | A maioria das tarefas |
| Alto | Tarefas complexas ou de alto risco |
| xhigh (extra alto) | Coding e tarefas agênticas de longa duração |
| Máx | Casos excepcionais; consomem o limite muito mais rápido |

## Analogias para explicar

- **Carros:** não faz sentido usar um carro de Fórmula 1 para ir à padaria. Cada tarefa pede um tipo de veículo.
- **Nomes literários:**
  - Haiku: poesia japonesa de 3 versos, curta e direta.
  - Sonnet (soneto): 14 versos, elegante e equilibrado.
  - Opus: uma sinfonia completa, com orquestra inteira.
  - Fable (fábula): o conto épico com valor moral.
  - Mythos (mito): a grande narrativa, como a Ilíada e a Odisseia.

## Correções ao material de treinamento

- O Fable **não** é "proibido" em cibersegurança, biologia ou P&D de IA — ele tem **salvaguardas adicionais** nessas áreas, o que pode deixar suas respostas mais restritivas ali. Trate como um alerta de comportamento, não como uma proibição.
- O Opus **não** é o modelo mais alto da linha: Fable e Mythos ficam acima.
- Modelo, esforço e pensamento são **controles independentes** — mas **Haiku não tem esforço**, e **Opus 5.5/Opus 5/Fable 5.1 não têm a opção de desligar o pensamento**. Confira sempre essa combinação antes de recomendar.
