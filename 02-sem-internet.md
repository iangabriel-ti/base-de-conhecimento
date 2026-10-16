# 02 — Sem acesso à internet (cabo de rede)

**Categoria:** Rede · **Prioridade sugerida:** Média a Alta · **Tempo médio N1:** 10 a 20 min

## Sintomas
- Ícone de rede com um "X" ou um globo com mensagem "Sem acesso à internet".
- Sites não abrem, mas sistemas internos funcionam (ou o contrário).

## Perguntas iniciais
1. Só o seu computador está sem internet, ou os colegas também?
2. Algum sistema interno funciona?
3. Alguém mudou o computador de mesa ou mexeu no cabo?

> Se vários usuários do mesmo setor estão sem rede, o problema provavelmente não está no computador. Escale logo para rede/infraestrutura e abra um chamado de incidente geral.

## Diagnóstico
Abra o **Prompt de Comando** e siga as camadas, de baixo para cima:

| Passo | Comando / ação | O que mostra |
|---|---|---|
| 1. Físico | Conferir o cabo e as luzes da placa de rede | Se há link com o switch |
| 2. Configuração | `ipconfig /all` | Se recebeu IP, máscara, gateway e DNS |
| 3. Rede local | `ping <gateway>` | Se alcança o roteador da rede |
| 4. Internet | `ping 8.8.8.8` | Se a saída para a internet funciona |
| 5. DNS | `nslookup google.com` | Se os nomes estão sendo resolvidos |

> 💡 O script [`diagnostico-rede.ps1`](https://github.com/iangabriel-ti/scripts-suporte) faz esses cinco testes automaticamente e mostra em qual etapa está a falha.

### Como interpretar
- **IP começando com 169.254.x.x:** o computador não recebeu IP do servidor DHCP. Verificar cabo e porta, e então renovar o IP.
- **Pinga o gateway, mas não o 8.8.8.8:** o problema está depois da rede local (firewall, link da operadora). Escalar.
- **Pinga o 8.8.8.8, mas sites não abrem:** problema de DNS ou de proxy.

## Solução
```cmd
:: Renovar o IP
ipconfig /release
ipconfig /renew

:: Limpar o cache de DNS
ipconfig /flushdns
```
- Desabilitar e habilitar o adaptador em **Configurações > Rede e Internet > Configurações de rede avançadas**.
- Testar outro cabo ou outra porta do ponto de rede.
- Se o proxy estiver configurado errado, conferir em **Configurações > Rede e Internet > Proxy** conforme o padrão da empresa.
- Último recurso no computador: `netsh winsock reset` seguido de reinicialização.

## Quando escalar
- Ponto de rede sem sinal (problema de cabeamento ou porta de switch).
- Vários usuários afetados.
- Falha depois do gateway (link, firewall, servidor DNS).

## Registro no chamado
Resultado do `ipconfig /all` (IP recebido), resultado de cada ping, ação que resolveu.
