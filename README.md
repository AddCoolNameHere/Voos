# NAV — Rastreador GPS de Voo Offline (versão leve)

Posição **GPS ao vivo no mapa-múndi, sem internet**. O mapa do mundo já vem embutido;
o detalhe de alta resolução é baixado **só da região da sua rota**, em faixas, e fica salvo offline (PWA).

Esta versão tem **poucos arquivos, todos na raiz** — dá pra publicar **pelo celular**, pelo site do GitHub.

## Publicar pelo CELULAR (GitHub Pages)
1. No navegador do celular, abra **github.com** → **+** → **New repository**.
   - Nome: `nav-gps-offline` · marque **Public** · crie.
2. Na página do repo: **Add file → Upload files**.
3. **Selecione TODOS os arquivos desta pasta de uma vez** (são poucos, todos na raiz) e aguarde subir.
4. Escreva uma mensagem e **Commit changes**.
5. **Settings → Pages → Branch: `main` / `/ (root)` → Save**.
6. Em ~1 min o app fica em: `https://SEU-USUARIO.github.io/nav-gps-offline/`

> Como todos os arquivos estão na raiz (sem subpastas), o Pages serve tudo direto.
> O `.nojekyll` é opcional aqui; se o celular não deixar enviar arquivo começando com ponto, pode ignorar.

## Como usar no avião
1. No wifi: abra o app → botão **ROTA** → marque **origem** e **destino** (toque no mapa) → escolha **Caminho (10m)** ou **Continente (50m)** → **Baixar detalhe da área**. (Opcional: "Adicionar à tela inicial".)
2. No avião: **Iniciar rastreamento** e permita a **Localização**. Modo avião pode ficar ligado.
3. 1ª leitura é mais rápida perto da **janela**.

## Arquivos (todos na raiz)
```
index.html              app (mapa-base embutido + lógica de faixas)
sw.js                   service worker (offline)
manifest.webmanifest    PWA
icon-192.png  icon-512.png
d10_0.json … d10_5.json detalhe 10m por faixa de 60° de longitude
d50_0.json … d50_5.json detalhe 50m por faixa de 60° de longitude
```
Cada faixa cobre 60° de longitude. Uma rota baixa só a(s) faixa(s) que cruza
(ex.: São Paulo→Buenos Aires = 1 faixa). Dados: Natural Earth / world-atlas (domínio público).
