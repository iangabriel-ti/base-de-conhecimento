# Computador lento: diagnóstico passo a passo

**Sintoma relatado pelo usuário:** "Meu computador está muito lento", "demora para ligar", "trava quando abro vários programas".

**Objetivo:** encontrar a **causa** antes de aplicar qualquer solução. Formatar resolve muita coisa, mas nem sempre é necessário.

---

## 1. Entender o problema (perguntas ao usuário)

- Quando começou? Foi depois de instalar algo ou de alguma atualização?
- É lento **sempre** ou só em alguma situação (ao ligar, ao abrir um programa específico, na internet)?
- Aparece alguma mensagem de erro, propaganda ou janela estranha?
- O computador esquenta ou faz barulho?

> 💡 As respostas já indicam o caminho: lento só na internet → problema de rede; lento ao ligar → programas de inicialização ou disco; propagandas → malware.

## 2. Gerenciador de Tarefas (`Ctrl + Shift + Esc`)

Na aba **Processos**, ordene por cada coluna e veja o que está consumindo recursos:

| Recurso | Sinal de problema | Causa provável |
|---|---|---|
| **CPU** | Sempre acima de 80% | Programa travado, malware, superaquecimento |
| **Memória** | Sempre acima de 80% | Pouca RAM para o uso → [upgrade de memória](../hardware/trocar-memoria-ram.md) |
| **Disco** | Muito tempo em 100% | HD lento ou com defeito → [trocar por SSD](../hardware/instalar-ssd.md) |

## 3. Programas de inicialização

1. Gerenciador de Tarefas → aba **Aplicativos de inicialização**
2. Desative o que não é necessário ao ligar (atualizadores, Spotify, Steam, programas de fabricante)
3. **Não desative** antivírus e drivers (áudio, touchpad, vídeo)

## 4. Saúde do disco

- Instale o **CrystalDiskInfo** e veja o *Estado de saúde*:
  - **Bom** → ok
  - **Cuidado / Ruim** → disco falhando. **Faça backup imediatamente** e substitua
- Verifique o espaço livre: deixe pelo menos **15%** do disco livre
- Limpeza: *Configurações → Sistema → Armazenamento → Arquivos temporários*

## 5. Vírus e programas indesejados

- [ ] Fazer uma verificação completa no **Windows Defender** (*Segurança do Windows → Proteção contra vírus e ameaças → Opções de verificação → Verificação completa*)
- [ ] Em *Aplicativos instalados*, desinstalar programas desconhecidos ou que o usuário não usa
- [ ] Conferir extensões estranhas no navegador

## 6. Arquivos do sistema

Abra o **Prompt de Comando como administrador** e execute, nesta ordem:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
sfc /scannow
```

- O **DISM** repara a imagem do Windows
- O **SFC** verifica e corrige arquivos corrompidos do sistema

## 7. Temperatura

- Superaquecimento faz o processador **reduzir a velocidade** para se proteger
- Sinais: ventoinha muito barulhenta, notebook quente, lentidão que piora com o uso
- Solução: limpeza interna (poeira), troca da **pasta térmica** e, no notebook, uso em superfície rígida

---

## ✅ Resumo da decisão

| Causa encontrada | Solução |
|---|---|
| Muitos programas na inicialização | Desativar os desnecessários |
| Memória sempre cheia | Upgrade de RAM |
| Disco em 100% ou HD lento | Trocar por SSD |
| Disco com saúde "Cuidado/Ruim" | Backup urgente + troca do disco |
| Malware | Remover; se persistir, formatar |
| Arquivos do sistema corrompidos | DISM + SFC; se persistir, formatar |
| Superaquecimento | Limpeza + pasta térmica |

## 📝 Registro

Documentar o atendimento usando o [modelo de registro de chamado](../modelos/registro-de-chamado.md).

---

📚 [Voltar para o índice](../README.md)
