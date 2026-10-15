# Como instalar um SSD e migrar do HD

**Quando usar:** computador demorando muito para ligar e abrir programas, disco sempre em 100% no Gerenciador de Tarefas, ou HD com sinais de defeito.

**Ganho esperado:** é o upgrade que mais melhora a velocidade de um computador antigo. O Windows passa a iniciar em segundos.

**Tempo estimado:** 30 minutos a 2 horas

---

## 1. Escolher o SSD certo

| Tipo | Formato | Onde encaixa |
|---|---|---|
| **SATA 2,5"** | Igual a um HD de notebook | No lugar do HD ou em uma baia livre, com cabo SATA |
| **M.2 SATA** | Placa pequena | Slot M.2 que aceite SATA |
| **M.2 NVMe** | Placa pequena, bem mais rápido | Slot M.2 que aceite NVMe |

**Como descobrir:** consulte o manual ou o site do fabricante do notebook/placa-mãe e veja se há slot M.2 e de qual tipo. Na dúvida, o **SATA 2,5"** é compatível com praticamente todos os PCs que têm HD.

**Capacidade:** mínimo de **240/256 GB** para o Windows e os programas.

## 2. Escolher o método

| Método | Vantagem | Quando usar |
|---|---|---|
| **A. Instalação limpa** | Sistema novo, sem vírus nem lixo | O Windows está lento ou com problemas |
| **B. Clonagem** | Mantém tudo como estava (programas e arquivos) | O Windows está bom e o usuário não quer reinstalar nada |

## 3. Instalação física

1. **Backup** dos arquivos importantes (sempre!)
2. Desligue o computador, tire da tomada e descarregue a eletricidade estática tocando no gabinete
3. Instale o SSD:
   - **SATA 2,5" no desktop:** prenda na baia e conecte o **cabo SATA** (na placa-mãe) e o **cabo de energia SATA** (da fonte)
   - **SATA 2,5" no notebook:** remova o HD, transfira o suporte/caddy para o SSD e encaixe no mesmo lugar
   - **M.2:** encaixe inclinado no slot, abaixe e prenda com o parafuso pequeno

## 4A. Instalação limpa

1. Siga o tutorial [Como formatar e instalar o Windows 11](../windows/formatar-e-instalar-windows.md), escolhendo o **SSD** como destino
2. Se o HD antigo continuar no computador, use-o depois como disco de **arquivos** (formate-o só depois de copiar o backup)

## 4B. Clonagem

1. Com o SSD conectado (dentro do PC ou por um **adaptador SATA-USB**), use um programa de clonagem. Muitos fabricantes de SSD oferecem um gratuito (ex.: Samsung Data Migration, Crucial/Acronis, Kingston/Acronis)
2. Escolha o **HD como origem** e o **SSD como destino**
3. Confira se o espaço **usado** no HD cabe no SSD. Se não couber, apague arquivos ou mova-os antes
4. Após clonar, coloque o SSD no lugar do HD (ou defina-o como primeiro no **boot** da BIOS)

## 5. Testes e ajustes

- [ ] Conferir se o Windows inicia pelo SSD (*Gerenciamento de Disco*: `diskmgmt.msc`)
- [ ] Verificar se o **TRIM** está ativo. No Prompt de Comando: `fsutil behavior query DisableDeleteNotify` → o resultado `= 0` significa ativado
- [ ] **Não** desfragmentar o SSD (o Windows já faz a otimização correta sozinho)
- [ ] Ver a saúde do SSD com o **CrystalDiskInfo**

---

## 🔧 Problemas comuns

| Problema | Solução |
|---|---|
| O SSD não aparece no Windows | É novo e não está inicializado: abra `diskmgmt.msc`, inicialize como **GPT** e crie um volume |
| O SSD não aparece na BIOS | Conferir cabos SATA e de energia; no M.2, confirmar se o slot aceita aquele tipo (SATA/NVMe) |
| Após clonar, o PC não inicia | Ajustar a ordem de boot na BIOS; conferir se o modo (UEFI/Legacy) é o mesmo de antes |
| O SSD aparece com espaço menor | A clonagem copiou o tamanho das partições do HD. Estender o volume no `diskmgmt.msc` |

---

📚 [Voltar para o índice](../README.md)
