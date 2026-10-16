# 07 — Outlook não envia ou não recebe e-mails

**Categoria:** E-mail · **Prioridade sugerida:** Média a Alta · **Tempo médio N1:** 10 a 30 min

## Sintomas
- E-mails parados na Caixa de Saída.
- Nenhum e-mail novo chega há horas.
- Barra inferior mostra "Desconectado" ou "Trabalhando offline".
- Pede a senha várias vezes.

## Perguntas iniciais
1. Pelo navegador (Outlook na Web) os e-mails chegam e saem normalmente?
2. O problema é com todos os destinatários ou com um específico?
3. Algum e-mail com anexo grande foi enviado agora há pouco?

> O teste no **Outlook na Web** separa o problema logo no começo: se lá funciona, o problema está no computador ou no aplicativo. Se lá também falha, o problema é na conta ou no servidor.

## Diagnóstico
1. Verificar a barra inferior do Outlook. Se mostrar "Trabalhando offline", desmarcar em **Enviar/Receber > Trabalhar Offline**.
2. Verificar a internet ([artigo 02](02-sem-internet.md)).
3. Procurar na Caixa de Saída algum e-mail com anexo grande que esteja travando a fila.
4. Verificar se a caixa postal está cheia (aviso de cota no Outlook).
5. Problema com um destinatário só: ler a mensagem de retorno (NDR), que diz o motivo (endereço inexistente, caixa cheia do destinatário, bloqueio).

## Solução
- Remover ou mover para Rascunhos o e-mail travado na Caixa de Saída e reenviar com o anexo menor ou por link de arquivo.
- Caixa cheia: orientar a apagar itens grandes e esvaziar a Lixeira e os Itens Excluídos.
- Pedido de senha repetido: atualizar a credencial no Gerenciador de Credenciais do Windows ou sair e entrar de novo na conta do Office.
- Abrir em modo de segurança para descartar suplementos com problema:
  ```cmd
  outlook.exe /safe
  ```
  Se funcionar, desativar os suplementos em **Arquivo > Opções > Suplementos**.
- Último recurso no computador: criar um **novo perfil** do Outlook (Painel de Controle > Email > Mostrar Perfis).

## Quando escalar
- Outlook na Web também falha (problema no servidor ou na conta).
- E-mails rejeitados por bloqueio ou lista de spam.
- Aumento de cota da caixa postal.

## Registro no chamado
Resultado do teste no Outlook na Web, mensagem de erro ou NDR, ação aplicada.
