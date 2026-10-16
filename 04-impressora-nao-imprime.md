# 04 — Impressora não imprime

**Categoria:** Impressão · **Prioridade sugerida:** Média · **Tempo médio N1:** 10 a 25 min

## Sintomas
- O documento vai para a fila e não sai.
- Mensagem "Impressora offline" ou "Erro ao imprimir".
- A impressora não aparece na lista do usuário.

## Perguntas iniciais
1. Outras pessoas conseguem imprimir nessa impressora?
2. A impressora mostra algum erro no visor (papel, toner, atolamento)?
3. Você está imprimindo na impressora certa? (É comum ter várias com nomes parecidos.)

## Diagnóstico
1. **Verificar a própria impressora:** ligada, com papel, sem atolamento e sem erro no visor.
2. **Se ninguém consegue imprimir:** o problema é na impressora ou no servidor de impressão. Testar o `ping <IP da impressora>` (o IP costuma aparecer no visor ou em uma página de configuração impressa pelo próprio equipamento).
3. **Se só o usuário não consegue:** abrir a fila (Configurações > Bluetooth e dispositivos > Impressoras e scanners > impressora > Abrir fila de impressão) e verificar se há trabalhos travados com "Erro".
4. Conferir se a impressora padrão está correta.

## Solução

### Limpar a fila travada (spooler)
Abrir o Prompt de Comando **como administrador**:
```cmd
net stop spooler
del /Q /F %systemroot%\System32\spool\PRINTERS\*
net start spooler
```
Depois, pedir ao usuário para mandar a impressão de novo.

### Outras ações
- Remover a impressora e adicionar de novo (pelo servidor de impressão ou pelo IP, conforme o padrão da empresa).
- Definir a impressora correta como padrão e desmarcar "Deixar o Windows gerenciar minha impressora padrão", quando o usuário estiver trocando de impressora sem perceber.
- Atolamento ou falta de toner: seguir o procedimento do equipamento ou acionar o fornecedor do contrato de impressão.

## Quando escalar
- Impressora sem resposta na rede para todos os usuários.
- Erro de hardware (fusor, placa, mensagem de serviço no visor).
- Driver novo que precisa ser publicado no servidor de impressão.

## Registro no chamado
Nome/IP da impressora, se o problema era geral ou só do usuário, mensagem de erro e ação que resolveu.
