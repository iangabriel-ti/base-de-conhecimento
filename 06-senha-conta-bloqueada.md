# 06 — Senha expirada ou conta bloqueada

**Categoria:** Acesso · **Prioridade sugerida:** Alta (usuário parado) · **Tempo médio N1:** 5 a 15 min

## Sintomas
- "A conta de usuário foi bloqueada e não pode ser usada para fazer logon."
- "Sua senha expirou e deve ser alterada."
- "O nome de usuário ou a senha está incorreto", mesmo o usuário tendo certeza da senha.

## Antes de tudo: confirmar a identidade
**Nunca redefina uma senha sem confirmar quem está pedindo.** Siga a política da empresa (por exemplo: matrícula, confirmação com o gestor ou ligação de volta para o ramal cadastrado). Pedidos de troca de senha são uma das formas mais usadas em golpes de engenharia social.

## Perguntas iniciais
1. Qual mensagem aparece exatamente?
2. Você trocou a senha recentemente?
3. Você usa essa conta em outros aparelhos (celular com e-mail corporativo, outro computador)?
4. O Caps Lock está ativado? O teclado está no layout certo (ABNT2)?

## Diagnóstico
1. Verificar Caps Lock, Num Lock e o idioma do teclado na tela de login.
2. Em ambiente com Active Directory, com as ferramentas e permissões de N1:
   ```powershell
   Get-ADUser -Identity <usuario> -Properties LockedOut, PasswordExpired, PasswordLastSet, Enabled |
     Select-Object Name, Enabled, LockedOut, PasswordExpired, PasswordLastSet
   ```
3. **Bloqueios repetidos** depois de desbloquear geralmente vêm de um aparelho com a **senha antiga salva** (celular, outro computador, unidade de rede mapeada com credencial salva).

## Solução
- **Conta bloqueada:** desbloquear no Active Directory (Usuários e Computadores do AD > propriedades do usuário > aba Conta > desbloquear) ou com:
  ```powershell
  Unlock-ADAccount -Identity <usuario>
  ```
- **Senha expirada ou esquecida:** redefinir com uma senha temporária e marcar **"O usuário deve alterar a senha no próximo logon"**.
- **Bloqueio que volta:** orientar o usuário a atualizar a senha no celular e em outros aparelhos e verificar o Gerenciador de Credenciais do Windows.
- Se a empresa tiver portal de autoatendimento de senha, orientar o usuário a se cadastrar para usar da próxima vez.

## Quando escalar
- Conta desabilitada (pode ser desligamento ou bloqueio intencional, confirmar com RH ou gestor).
- Bloqueios constantes sem aparelho identificado (pode ser tentativa de acesso indevido, acionar segurança).
- Falta de permissão do N1 para a unidade organizacional do usuário.

## Registro no chamado
Como a identidade foi confirmada, situação encontrada (bloqueada, expirada, desabilitada), ação tomada e orientação dada. **Nunca anote a senha no chamado.**
