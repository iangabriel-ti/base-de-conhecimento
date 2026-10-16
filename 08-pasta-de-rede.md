# 08 — Pasta de rede não abre

**Categoria:** Rede / Acesso · **Prioridade sugerida:** Média · **Tempo médio N1:** 10 a 20 min

## Sintomas
- A unidade mapeada (por exemplo, `S:`) aparece com um "X" vermelho.
- "O Windows não pode acessar \\servidor\pasta."
- "Você não tem permissão para acessar esta pasta."

## Perguntas iniciais
1. Os colegas do mesmo setor conseguem abrir essa pasta?
2. Você já tinha acesso antes ou é a primeira vez?
3. A sua senha foi trocada recentemente?

## Diagnóstico
1. Verificar a conexão de rede ([artigo 02](02-sem-internet.md)). Se estiver em home office, conferir se a VPN está conectada.
2. Testar se o servidor responde:
   ```cmd
   ping <nome-do-servidor>
   ```
3. Tentar abrir o caminho completo pelo Explorador de Arquivos: `\\servidor\pasta`.
4. Listar as unidades mapeadas:
   ```cmd
   net use
   ```
   Status "Indisponível" ou "Desconectado" indica que a ligação caiu.
5. **Erro de permissão** é diferente de **erro de acesso**: com permissão negada, o servidor respondeu, mas o usuário não está no grupo que tem acesso.

## Solução
- Remover e mapear a unidade de novo:
  ```cmd
  net use S: /delete
  net use S: \\servidor\pasta /persistent:yes
  ```
- Senha alterada: atualizar a credencial salva no Gerenciador de Credenciais do Windows.
- Primeira vez ou acesso negado: **não conceder permissão por conta própria**. Pedir a aprovação do responsável pela pasta (normalmente o gestor da área) e encaminhar conforme o processo.

## Quando escalar
- Servidor sem resposta para todos.
- Pedido de inclusão em grupo de acesso (com a aprovação anexada ao chamado).
- Pasta ou arquivos que sumiram (pode ser necessário restaurar do backup).

## Registro no chamado
Caminho da pasta, mensagem de erro, se o problema era de conexão ou de permissão, aprovação (quando houver) e ação tomada.
