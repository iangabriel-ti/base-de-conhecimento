# 05 — Computador lento

**Categoria:** Desempenho · **Prioridade sugerida:** Baixa a Média · **Tempo médio N1:** 20 a 40 min

## Sintomas
- Demora para ligar ou para abrir programas.
- Travamentos rápidos, cursor "carregando" o tempo todo.
- Ventoinha muito barulhenta ou equipamento muito quente.

## Perguntas iniciais
1. Desde quando está lento? Começou depois de alguma instalação ou atualização?
2. É lento o tempo todo ou só em um programa específico? Se for só na internet, ver o [artigo 02](02-sem-internet.md).
3. Quando foi a última vez que o computador foi reiniciado (não apenas a tampa fechada)?
4. Aparecem propagandas, janelas estranhas ou programas que você não instalou?

> As respostas já indicam o caminho: lento ao ligar aponta para inicialização ou disco; propagandas apontam para malware; lentidão que piora com o uso aponta para superaquecimento.

## Diagnóstico
1. **Tempo ligado:** Gerenciador de Tarefas (`Ctrl + Shift + Esc`) > Desempenho > CPU > campo "Tempo de atividade". Muitos dias sem reiniciar é causa frequente.
2. **Uso de recursos:** na aba Processos, ordenar por CPU, Memória e Disco e anotar o que mais consome:

   | Recurso | Sinal de problema | Causa provável |
   |---|---|---|
   | CPU | Sempre acima de 80% | Programa travado, malware, superaquecimento |
   | Memória | Sempre acima de 80% | Pouca RAM para o uso (ver o [artigo 10](10-trocar-memoria-ram.md)) |
   | Disco | Muito tempo em 100% | HD mecânico lento ou com defeito (ver o [artigo 11](11-instalar-ssd.md)) |

3. **Inicialização:** aba Aplicativos de inicialização. Verificar programas desnecessários com impacto "Alto".
4. **Espaço em disco:** o disco do sistema com menos de 10% a 15% livre deixa o Windows lento.
5. **Saúde do disco:**
   ```powershell
   Get-PhysicalDisk | Select-Object FriendlyName, MediaType, HealthStatus
   ```
   Para mais detalhes, o programa gratuito **CrystalDiskInfo** mostra o estado como Bom, Cuidado ou Ruim.
6. **Malware:** verificação completa no Windows Defender (Segurança do Windows > Proteção contra vírus e ameaças > Opções de verificação > Verificação completa).
7. **Integridade do sistema:** no Prompt de Comando como administrador:
   ```cmd
   sfc /scannow
   ```
8. **Temperatura:** ventoinha sempre no máximo e lentidão que piora com o tempo indicam que o processador está reduzindo a velocidade para se proteger.

## Solução

| Causa encontrada | Ação |
|---|---|
| Muitos dias sem reiniciar | Reiniciar e orientar o usuário a reiniciar pelo menos uma vez por semana |
| Programas na inicialização | Desativar os desnecessários (nunca antivírus e drivers de áudio, vídeo ou touchpad) |
| Pouco espaço em disco | Limpeza de Disco (`cleanmgr`), Sensor de Armazenamento ou o script [`limpeza-temporarios.ps1`](https://github.com/iangabriel-ti/scripts-suporte) |
| Atualizações pendentes | Instalar pelo Windows Update |
| Programa consumindo recursos de forma anormal | Encerrar, atualizar ou reinstalar |
| Arquivos do sistema corrompidos | Se o `sfc` não conseguir reparar, rodar `DISM /Online /Cleanup-Image /RestoreHealth` e depois o `sfc /scannow` de novo |
| Memória sempre cheia | Pedido de upgrade de RAM ([artigo 10](10-trocar-memoria-ram.md)) |
| HD mecânico em 100% | Pedido de troca por SSD ([artigo 11](11-instalar-ssd.md)) |
| Superaquecimento | Limpeza interna e troca da pasta térmica (N2, se a política não permitir abrir o equipamento) |

## Quando escalar
- Disco com `HealthStatus` diferente de "Healthy" ou "Cuidado/Ruim" no CrystalDiskInfo: **fazer backup imediatamente** e pedir a troca.
- Suspeita de malware (processos desconhecidos, pop-ups, antivírus desativado): **isolar o equipamento da rede** e acionar a segurança.
- Equipamento abaixo da especificação mínima para o trabalho do usuário (pedido de upgrade).

## Registro no chamado
Tempo de atividade, processos com maior consumo, espaço livre em disco, estado de saúde do disco, ações feitas e percepção do usuário depois do atendimento. Modelo: [registro de chamado](modelos/registro-de-chamado.md).
