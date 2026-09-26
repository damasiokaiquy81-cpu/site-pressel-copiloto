# site-pressel-copiloto

Pressel do CopilotoVendas.ai — 3 perguntas rápidas e, no fim, o convite para a página de vendas.

## Arquivos

- `index.html` — as 3 perguntas, a tela final e o envio das respostas.
- `assets/` — logo, favicon e a fonte Inter (licença em `assets/OFL.txt`).
- O SQL (função `registrar_pressel`) fica em `..\Supabase\3-pressel.sql`, junto com tudo do Supabase.

## Antes de publicar

No `<script>` do `index.html`:
- `SUPABASE_URL` e `SUPABASE_KEY` — Project URL e chave **publishable** do projeto novo (a mesma do app).
- O `href` do botão final (`id="go"`) — endereço do site de vendas.

## Respostas

São gravadas pela função `registrar_pressel`, com a chave publicável do projeto (a mesma do app).
Não é guardado nome, e-mail nem nada pessoal — só um código aleatório do aparelho, as respostas,
se é celular ou computador, e o sistema. Mudou as opções? Ajuste o `..\Supabase\3-pressel.sql` e rode de novo no SQL Editor.

## Botão final

`Ver o Copiloto funcionando` leva para a página de vendas com `?d=<código do aparelho>` — o mesmo código
salvo nas respostas. Se a pessoa comprar, a venda guarda esse código e a visão `vendas_com_pressel`
(arquivo `..\Supabase\4-vendas.sql`) mostra a compra junto com as respostas da pressel.

## Rodar local

Sirva a pasta por HTTP em vez de abrir o arquivo por duplo clique — com Node instalado:

```
npx --yes serve .
```
