# Como trocar ou adicionar memória RAM

**Quando usar:** computador lento com muitas abas ou programas abertos, uso de memória sempre acima de 80% no Gerenciador de Tarefas, ou pente de memória com defeito.

**Tempo estimado:** 15 a 30 minutos

---

## 1. Descobrir a memória compatível

Antes de comprar, é preciso saber:

| Informação | Onde ver |
|---|---|
| Quantidade instalada e velocidade | Gerenciador de Tarefas (`Ctrl + Shift + Esc`) → **Desempenho → Memória** |
| Slots usados e livres | Mesma tela, em **Slots usados** (ex.: "1 de 2") |
| Tipo (DDR3, DDR4, DDR5) | Programa **CPU-Z**, aba *Memory* e *SPD* |
| Máximo suportado | Site do fabricante do notebook ou da placa-mãe |

**Regras importantes:**
- **Desktop** usa pente **DIMM** (comprido); **notebook** usa **SODIMM** (curto)
- DDR3, DDR4 e DDR5 **não são compatíveis entre si**: o encaixe é diferente
- Para **dual channel** (melhor desempenho), use dois pentes iguais (mesma capacidade e velocidade)
- Alguns notebooks têm memória **soldada** na placa e não permitem upgrade. Confira antes de comprar

## 2. Preparação

- [ ] Desligar o computador **completamente** e tirar da tomada
- [ ] Em notebooks, desconectar a bateria, se for removível ou acessível
- [ ] Segurar o botão de ligar por 5 segundos para descarregar a energia restante
- [ ] Encostar em uma parte metálica do gabinete para descarregar a **eletricidade estática**
- [ ] Ferramentas: chave Phillips e uma espátula plástica (para notebooks)

## 3. Instalação

### Desktop
1. Abra a tampa lateral do gabinete
2. Localize os slots de memória ao lado do processador
3. Abra as travas das pontas do slot
4. Alinhe o **chanfro** (o recorte no meio dos contatos) com o slot. Ele só encaixa em uma posição
5. Pressione firme com os dois polegares até as travas fecharem sozinhas (ouve-se um "clique")
6. Para dual channel, consulte o manual da placa: normalmente se usam os slots **A2 e B2** (o 2º e o 4º)

### Notebook
1. Remova os parafusos da tampa inferior e solte-a com a espátula
2. Para remover um pente: afaste as duas presilhas laterais; o pente levanta sozinho em ângulo
3. Encaixe o novo pente **inclinado a cerca de 30°** até o fim e empurre para baixo até as presilhas travarem

## 4. Testes

- [ ] Ligar o computador e conferir se a **quantidade total** aparece no Gerenciador de Tarefas
- [ ] Rodar o **Diagnóstico de Memória do Windows** (`mdsched.exe`) para verificar erros
- [ ] Usar normalmente por alguns minutos com vários programas abertos

---

## 🔧 Problemas comuns

| Problema | Solução |
|---|---|
| Computador liga mas não dá vídeo (tela preta, apitos) | Pente mal encaixado: remova e encaixe de novo com mais firmeza |
| A memória nova não é reconhecida | Testar cada pente sozinho; conferir se é o tipo certo e se o slot funciona |
| Tela azul depois do upgrade | Pentes de velocidades diferentes ou defeito. Rodar o `mdsched.exe` e testar cada pente separadamente |
| Primeira inicialização demora | Normal em alguns PCs: a placa-mãe está "treinando" a nova memória. Aguarde |

---

📚 [Voltar para o índice](../README.md)
