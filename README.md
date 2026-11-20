# Concierge

Porteiro dos apps com voz: **Fullfin**, **Trabalho de Homem** (TDH) e **Prev** (CRM das mães).

Fala uma vez → a function `concierge-voz` (previmater-ops) transcreve e diz **o app** e se é **pergunta** ou **comando**.

- **Pergunta** (v1.2.0): responde aqui, na tela e em voz alta. Cada app fica aberto escondido (`?situacao=1`) e devolve o mesmo resumo do assistente dele, com as contas das telas; a voz do app (`tdh-voz` / `fullfin-voz` / `prev-voz`) responde com esse resumo. Se a voz achar que era comando, abre o app na confirmação.
- **Conversa** (v1.3.0): as respostas ficam empilhadas na tela, em cima do botão. Continua sendo toque para falar e toque para enviar; tocar enquanto ele fala corta a voz e já grava. As últimas 3 trocas do mesmo app vão junto (`historico`), então "e a Juliana?" funciona; pergunta sem app vai para o app da conversa (comando nunca). Conversa só em memória, zera em 10 min parada ou em "Nova conversa". Voz natural pela `concierge-fala` (TTS da OpenAI); se falhar, usa a voz do aparelho. A voz diz o campo `fala` (1–2 frases) e a tela mostra a resposta completa.
- **Comando**: abre o app certo com `?voz_texto=...`, na tela de confirmação. Nada é gravado pelo Concierge.

Nome do app falado decide: "TDH" (ou "TDAH"), "Fullfin", "Prev"/"CRM". "PreviMater" é o centro de custo do Fullfin, não o app. Em comando, o nome do app não passa por cima das travas de contar duas vezes (obra ou parcela de mãe no Fullfin vira dúvida).

Login próprio (`concierge_sess`). Os apps escondidos usam o passe do Concierge só em memória e nunca renovam nem gravam o login deles: renovar a mesma chave em dois lugares derruba a sessão.
