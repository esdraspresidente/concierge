# Concierge

Porteiro dos apps com voz. Fala uma vez → a function `concierge-voz` (previmater-ops) transcreve e decide se é do **Fullfin**, do **Trabalho de Homem** ou da **PreviMater** (CRM) → abre o app certo com `?voz_texto=...` → o app manda o texto para a própria voz (`fullfin-voz` / `tdh-voz` / `prev-voz`) e abre a tela de confirmação.

Nada é gravado pelo Concierge. Gasto de obra vai sempre para o Trabalho de Homem; parcela paga por mãe vai sempre para o CRM da PreviMater (o Fullfin importa depois). Na dúvida, ele pergunta.
