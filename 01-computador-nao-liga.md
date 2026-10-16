# 01 — Computador não liga

**Categoria:** Hardware · **Prioridade sugerida:** Alta (usuário parado) · **Tempo médio N1:** 15 a 30 min

## Sintomas
- Nada acontece ao apertar o botão (sem luz, sem ventoinha, sem som).
- Liga as luzes e as ventoinhas, mas a tela fica preta.
- Liga e desliga sozinho em poucos segundos.
- Emite bipes ao ligar.

## Perguntas iniciais
1. Aparece alguma luz no computador ou no monitor?
2. Houve queda de energia, mudança de lugar ou alguém mexeu nos cabos?
3. É notebook ou desktop? Se for notebook, está na tomada?
4. Aconteceu algo antes (atualização, travamento, líquido derramado)?

## Diagnóstico (do mais simples ao mais complexo)

### Cenário A — nenhum sinal de energia
1. Confirmar se a tomada funciona (ligar outro aparelho nela).
2. Verificar o cabo de força nas duas pontas e a chave do estabilizador/filtro de linha.
3. Desktop: verificar a chave liga/desliga da fonte, na parte de trás do gabinete.
4. Notebook: testar com outro carregador compatível, se houver.
5. Notebook: fazer o **reset de energia** — desligar da tomada, segurar o botão de ligar por 30 segundos e tentar de novo.

### Cenário B — liga, mas a tela fica preta
1. Conferir se o monitor está ligado e na entrada certa (HDMI, DisplayPort, VGA).
2. Reconectar o cabo de vídeo nas duas pontas. Se possível, testar outro cabo.
3. Verificar se o cabo está na placa de vídeo dedicada (quando existir), e não na saída da placa-mãe.
4. Notebook: tentar a combinação de teclas para alternar a tela (geralmente `Win + P`) ou ligar um monitor externo.
5. Pressionar `Win + Ctrl + Shift + B` para reiniciar o driver de vídeo.

### Cenário C — bipes ou desliga sozinho
1. Anotar a sequência de bipes (quantidade e duração) e consultar o manual do fabricante da placa-mãe.
2. Bipes de memória são comuns: com o equipamento desligado e sem energia, reencaixar os pentes de RAM (passo a passo no [artigo 10](10-trocar-memoria-ram.md)).
3. Desligar sozinho pode indicar superaquecimento: verificar se as ventoinhas giram e se há poeira acumulada.

## Solução
| Causa encontrada | Ação |
|---|---|
| Tomada, cabo ou estabilizador | Trocar a tomada ou o cabo e registrar |
| Monitor na entrada errada | Ajustar a entrada e orientar o usuário |
| Carregador com defeito | Substituir por um da reserva e abrir pedido de troca |
| Memória mal encaixada | Reencaixar e testar (se a política permitir abrir o equipamento) |

## Quando escalar (N2 ou fornecedor)
- Fonte, placa-mãe ou placa de vídeo com suspeita de defeito.
- Equipamento com líquido derramado ou cheiro de queimado (**não ligar novamente**).
- Equipamento em garantia, porque abrir pode cancelar a garantia.
- Se o usuário não pode ficar parado, solicitar um equipamento reserva.

## Registro no chamado
Relato do usuário, cenário identificado (A, B ou C), testes feitos e resultado de cada um, solução aplicada ou motivo do escalonamento.
