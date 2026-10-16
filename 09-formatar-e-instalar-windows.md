# 09 — Formatar e instalar o Windows 11

**Categoria:** Windows · **Tipo:** Procedimento · **Tempo estimado:** 1 a 2 horas (sem contar o backup)

**Quando usar:** computador muito lento, infectado por vírus, com erros frequentes do sistema ou ao trocar o disco por um novo. Antes de formatar, siga o diagnóstico do [artigo 05](05-computador-lento.md): muitas vezes não é necessário.

---

## ⚠️ Antes de começar

- [ ] **Backup** dos arquivos do usuário: Documentos, Área de Trabalho, Downloads, Imagens e favoritos do navegador
- [ ] Anotar os **programas** que o usuário usa e as licenças (Office, antivírus etc.)
- [ ] Confirmar que o computador atende aos **requisitos do Windows 11**:
  - Processador compatível de 64 bits
  - 4 GB de RAM (recomendado 8 GB)
  - 64 GB de armazenamento
  - TPM 2.0 e Secure Boot (verificar em `tpm.msc` e nas configurações da BIOS/UEFI)
- [ ] Pen drive de **8 GB ou mais** (ele será apagado)

> 💡 **Dica:** se o PC não atende aos requisitos do Windows 11, instale o Windows 10 seguindo os mesmos passos.

---

## 1. Criar o pen drive de instalação

1. Em outro computador, acesse o site oficial da Microsoft: **microsoft.com/software-download/windows11**
2. Baixe a **Ferramenta de Criação de Mídia** (*Media Creation Tool*)
3. Execute, aceite os termos e escolha **Unidade flash USB**
4. Selecione o pen drive e aguarde o download e a gravação

## 2. Iniciar o computador pelo pen drive

1. Conecte o pen drive e ligue o computador
2. Aperte a tecla do **menu de boot** logo ao ligar. Varia por fabricante:

| Fabricante | Tecla comum |
|---|---|
| Dell | F12 |
| Lenovo | F12 |
| HP | F9 ou Esc |
| Acer | F12 |
| Placas ASUS | F8 |
| Placas Gigabyte | F12 |

3. Escolha o pen drive (geralmente aparece como **UEFI: nome do pen drive**)

## 3. Instalar o Windows

1. Escolha idioma, formato de hora e teclado (**Português (Brasil) – ABNT2**)
2. Clique em **Instalar agora**
3. Chave do produto: se o computador já tinha Windows ativado, clique em **Não tenho uma chave do produto**. A ativação é feita automaticamente pela licença digital depois da instalação
4. Escolha a mesma edição que estava instalada (Home ou Pro)
5. Escolha **Personalizada: instalar apenas o Windows**
6. Na tela de partições: **exclua** as partições do disco onde o Windows estava, deixando "Espaço não alocado", selecione esse espaço e clique em **Avançar**

> ⚠️ **Atenção:** confira o disco certo antes de excluir. Se houver um segundo disco com arquivos do usuário, não mexa nele.

7. Aguarde: o computador vai reiniciar algumas vezes. **Remova o pen drive** na primeira reinicialização

## 4. Configuração inicial

1. Escolha região e teclado
2. Conecte à internet e entre com a **conta Microsoft** do usuário (ou crie uma conta local, se for o caso)
3. Configure as opções de privacidade

## 5. Pós-instalação (checklist)

- [ ] **Windows Update:** instalar todas as atualizações (repetir até não haver mais nenhuma)
- [ ] **Drivers:** conferir no **Gerenciador de Dispositivos** (`devmgmt.msc`) se há algum com ⚠️. Baixar os que faltarem do site do fabricante
- [ ] **Ativação:** conferir em *Configurações → Sistema → Ativação*
- [ ] Instalar navegador, leitor de PDF, Office e os programas anotados no início
- [ ] **Restaurar o backup** dos arquivos do usuário
- [ ] Testar áudio, Wi-Fi, câmera, impressora e periféricos
- [ ] Criar um **ponto de restauração**

---

## 🔧 Problemas comuns

| Problema | Solução |
|---|---|
| O pen drive não aparece no menu de boot | Testar outra porta USB; verificar se o boot está em modo UEFI na BIOS |
| "Este PC não pode executar o Windows 11" | Ativar TPM e Secure Boot na BIOS ou instalar o Windows 10 |
| Nenhum disco aparece na instalação | Falta o driver do controlador (comum em notebooks Intel com RST/VMD). Baixar o driver do site do fabricante e carregar pelo botão **Carregar driver** |
| Sem internet após instalar | Instalar o driver de rede pelo site do fabricante, usando outro computador |

## Quando escalar
- Equipamento corporativo: seguir a imagem padrão da empresa (instalação por rede ou ferramenta de implantação), que normalmente é feita pelo N2.
- Dados do usuário que não puderam ser copiados (disco com defeito): acionar o N2 para tentativa de recuperação **antes** de formatar.

## Registro no chamado
Motivo da formatação, confirmação do backup, edição do Windows instalada, drivers e programas instalados, testes feitos. Modelo: [registro de chamado](modelos/registro-de-chamado.md).
