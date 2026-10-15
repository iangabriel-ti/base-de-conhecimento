# Modelo de registro de chamado

Modelo para documentar atendimentos de suporte, no padrão usado em sistemas de service desk (GLPI, Jira, ServiceNow). Um bom registro permite que **qualquer pessoa da equipe** entenda o que aconteceu e resolva mais rápido se o problema voltar.

---

## 📋 Modelo

```
CHAMADO Nº: ____        DATA: __/__/____        PRIORIDADE: Baixa / Média / Alta / Crítica

SOLICITANTE: ______________________   SETOR: ______________
EQUIPAMENTO: ______________________   (modelo, patrimônio ou nome do PC)

1. PROBLEMA RELATADO
   (nas palavras do usuário)

2. DIAGNÓSTICO
   (o que foi verificado e o que foi encontrado)

3. CAUSA RAIZ
   (por que o problema aconteceu)

4. SOLUÇÃO APLICADA
   (passo a passo do que foi feito)

5. TESTES
   (como foi confirmado que está resolvido)

6. PREVENÇÃO / RECOMENDAÇÕES
   (o que fazer para não acontecer de novo)

STATUS: Resolvido / Pendente / Encaminhado para: ______
TEMPO DE ATENDIMENTO: ____
```

---

## ✍️ Exemplo preenchido

*Exemplo ilustrativo, baseado em um caso típico de atendimento.*

```
CHAMADO Nº: 001         DATA: 10/10/2026        PRIORIDADE: Média

SOLICITANTE: Familiar (usuário doméstico)
EQUIPAMENTO: Notebook, Intel Core i5, 8 GB RAM, HD 1 TB

1. PROBLEMA RELATADO
   "O notebook demora uns 5 minutos para ligar e trava quando abro o navegador."

2. DIAGNÓSTICO
   - Gerenciador de Tarefas: disco em 100% por vários minutos após o login
   - CPU e memória em níveis normais
   - 12 programas configurados para iniciar com o Windows
   - CrystalDiskInfo: saúde do HD em "Cuidado", com setores realocados

3. CAUSA RAIZ
   HD mecânico com desgaste, agravado pelo excesso de programas na inicialização.

4. SOLUÇÃO APLICADA
   - Backup dos arquivos do usuário
   - Substituição do HD por SSD SATA de 480 GB
   - Instalação limpa do Windows 11 e dos drivers
   - Restauração dos arquivos e reinstalação dos programas usados

5. TESTES
   - Windows inicia em cerca de 20 segundos
   - Navegador abre sem travamentos
   - CrystalDiskInfo: SSD com saúde "Bom"

6. PREVENÇÃO / RECOMENDAÇÕES
   - Evitar instalar programas desnecessários
   - Manter o Windows atualizado
   - Fazer backup periódico em nuvem ou HD externo

STATUS: Resolvido
TEMPO DE ATENDIMENTO: 2h30
```

---

📚 [Voltar para o índice](../README.md)
