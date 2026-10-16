# 03 — Wi-Fi conectado, mas sem internet

**Categoria:** Rede · **Prioridade sugerida:** Média · **Tempo médio N1:** 10 a 20 min

## Sintomas
- O notebook mostra "Conectado, sem internet" ou fica em "Identificando...".
- A rede Wi-Fi da empresa não aparece na lista.
- A conexão cai e volta várias vezes.

## Perguntas iniciais
1. Outras pessoas no mesmo lugar estão conectadas?
2. O problema acontece em qualquer lugar do prédio ou só em uma sala?
3. A senha da sua conta mudou recentemente? (Redes corporativas muitas vezes usam o mesmo usuário e senha da rede.)

## Diagnóstico
1. Conferir se o modo avião está desligado e o Wi-Fi ativado (tecla de função no notebook ou na Central de Ações).
2. Verificar se a rede aparece na lista. Se não aparecer só neste equipamento, o problema é no adaptador.
3. Rodar `ipconfig /all` e verificar se o adaptador Wi-Fi recebeu IP (atenção ao 169.254.x.x).
4. Testar `ping <gateway>` e `ping 8.8.8.8`, como no [artigo 02](02-sem-internet.md).
5. Ver detalhes do sinal e da rede:
   ```cmd
   netsh wlan show interfaces
   ```
   Observar o campo **Sinal**. Abaixo de 50% já pode causar quedas.

## Solução
- **Esquecer a rede e conectar de novo:** Configurações > Rede e Internet > Wi-Fi > Gerenciar redes conhecidas > Esquecer.
- Atualizar a senha da rede, se a senha da conta foi trocada.
- Desabilitar e habilitar o adaptador Wi-Fi.
- Usar a **Redefinição de rede** do Windows (Configurações > Rede e Internet > Configurações de rede avançadas > Redefinição de rede). Isso remove e reinstala os adaptadores e pede reinicialização. Avise o usuário antes.
- Sinal fraco: orientar o usuário a se aproximar do ponto de acesso e registrar o local, para a equipe de infraestrutura avaliar a cobertura.

## Quando escalar
- Rede não aparece para ninguém naquela área (ponto de acesso desligado ou com defeito).
- Problema de autenticação que continua depois de confirmar usuário e senha (certificado ou configuração do servidor).
- Driver do adaptador que precisa de pacote específico do fabricante, quando o usuário não tem permissão de instalação.

## Registro no chamado
Local do usuário, força do sinal, IP recebido, ações feitas e se o problema voltou.
