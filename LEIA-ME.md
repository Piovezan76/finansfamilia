# FinansFamília — Fase 1 (MVP)

Assistente financeiro da família: despesas e receitas, orçamento por categoria, dashboard e conciliação com extrato bancário. Funciona no iPhone e no PC. **Todos os dados ficam no seu dispositivo** — nada é enviado a servidores e nenhuma senha bancária é pedida, nunca.

## O que tem nesta pasta

| Arquivo | Para quê |
|---|---|
| `index.html` | O aplicativo completo (tudo em um arquivo) |
| `manifest.webmanifest` + `sw.js` + `icon-*.png` | Tornam o app instalável e com funcionamento offline |
| `exemplo_extrato.ofx` | Extrato de teste para experimentar a conciliação |
| `LEIA-ME.md` | Este guia |

## Como colocar no ar (5 minutos, grátis)

O app precisa de um endereço **https** para ser instalável no iPhone. Qualquer opção abaixo funciona:

1. **Netlify Drop (mais fácil):** acesse `app.netlify.com/drop`, arraste esta pasta inteira para a página e pronto — você recebe um endereço tipo `https://seunome.netlify.app`. Só você conhece o endereço.
2. **Vercel:** crie conta em `vercel.com`, "Add New → Project", envie a pasta.
3. **GitHub Pages:** suba os arquivos num repositório e ative Pages em Settings.

## Como instalar

- **iPhone:** abra o endereço no **Safari** → botão Compartilhar (⬆️) → **"Adicionar à Tela de Início"**. O app abre em tela cheia, com ícone, e funciona offline.
- **PC:** abra o mesmo endereço no Chrome ou Edge → clique no ícone de instalação (⊕) na barra de endereço.
- Sem publicar, você também pode simplesmente abrir o `index.html` com dois cliques no PC — tudo funciona, só não "instala".

## Como usar

1. Em **⚙️ Configurações** (toque nos avatares), coloque os nomes dos dois membros da família.
2. Botão **+** para lançar despesas e receitas (com parcelamento automático).
3. Em **🎯 Orçamento**, defina o teto mensal de cada categoria.
4. Em **🏦 Extratos**, importe o arquivo OFX/CSV baixado do seu banco: o app concilia automaticamente o que bater com seus lançamentos e sugere categoria para o resto. Teste com o `exemplo_extrato.ofx`.
5. Em **Configurações → Planilha e backup**, exporte o CSV (abre no Excel / importa no Google Sheets) e gere backups JSON.

## Dados e privacidade

- Os dados ficam salvos no navegador de cada dispositivo (armazenamento local).
- Para levar os dados do iPhone ao PC (ou vice-versa) na Fase 1, use **backup JSON → restaurar**.
- A sincronização automática entre aparelhos + planilha Google (Fase 2), a conciliação de PDF de fatura (Fase 3) e o assistente no WhatsApp (Fase 4) estão especificados no documento do projeto.

## Roteiro das próximas fases

- **Fase 2:** conta na nuvem (Supabase) para sincronização iPhone ↔ PC em tempo real + integração Google Sheets + exportar .xlsx.
- **Fase 3:** parser de PDF de fatura (Nubank, Itaú, Bradesco, Santander, BB, Caixa, Inter, C6) e regras de categorização mais espertas.
- **Fase 4:** bot no WhatsApp (texto, foto de cupom e áudio) via WhatsApp Business API.
- **Fase 5:** metas, lembretes, insights automáticos e divisão de despesas do casal.
