escolha-de-modelo
Skill para Claude que recomenda qual modelo usar (Haiku, Sonnet, Opus ou Fable), com qual nível de Esforço e se o Pensamento deve ficar ligado, para uma tarefa específica — sempre com justificativa curta.
O que ela faz
Quando instalada, a skill ativa automaticamente sempre que você perguntar algo como:
"qual modelo usar?"
"qual esforço?"
"preciso do Opus?"
"vale usar o Fable?"
"estou gastando muito limite"
"por que a resposta veio rasa?"
ou quando você simplesmente descrever uma tarefa e quiser saber a melhor configuração antes de começar — mesmo sem usar a palavra "modelo".
A recomendação segue uma árvore de decisão de 6 perguntas e leva em conta o suporte real de Esforço e Pensamento por modelo, além de exemplos práticos por área de trabalho.
Estrutura
```
escolha-de-modelo/
├── SKILL.md                 # lógica principal da skill
└── references/
    ├── modelos.md            # tabela de suporte esforço/pensamento por modelo
    └── exemplos.md            # exemplos de recomendação por área
```
Como instalar
Baixe esta pasta inteira (`escolha-de-modelo/`, mantendo a subpasta `references/`).
No Claude, vá em Configurações → Skills e adicione a pasta como uma skill personalizada.
A skill passa a ativar sozinha nas perguntas descritas acima — não precisa invocar por nome.
Licença
Sem licença restritiva declarada — use e adapte livremente.
