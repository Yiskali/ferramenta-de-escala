# Escala Mensal de Trabalho — HU Brasil

Ferramenta para montar, conferir e exportar a escala mensal de trabalho da sua equipe. Ela confere as regras enquanto você lança e mostra o saldo de horas de cada empregado na hora.

## Como baixar e abrir

1. Clique no arquivo **`index.html`**, na lista de arquivos acima.
2. Clique no botão de download (**Download raw file**), no canto direito.
3. Salve o arquivo numa pasta do seu computador.
4. Dê dois cliques no arquivo. Ele abre no navegador (**Chrome** ou **Edge**).

Não precisa instalar nada nem estar conectado à internet.

## Passo a passo

1. **Administração:** informe o nome do HU e da escala e cadastre os empregados, com matrícula, cargo (da lista ou digitado), CH semanal (de 1h a 40h) e, se houver, as horas convertidas em Disponibilidade Alcançável (DA). Dá para colar a lista direto do Excel.
2. **Feriados:** clique em **Carregar nacionais** e inclua os feriados locais e os pontos facultativos. Também dá para colar do Excel ou importar um arquivo .csv.
3. **Escala:** escolha o mês, clique no dia e escolha a sigla no painel à direita, ou digite direto na célula (ex.: `MT22`, `D12 AT`).
4. **Observações:** selecione o dia e escreva a troca de plantão ou outra ocorrência em **Observação do dia**. Há também um campo de observações do mês.
5. **Conferir:** veja o **Saldo** de cada empregado e clique em **Inconsistências** para ver o que está fora das regras.
6. **Exportar:** gere a planilha Excel (do mês ou do ano) ou o arquivo de importação do MentorH.

## O que o sistema confere

- 7 ou mais dias seguidos de trabalho, contando o fim do mês anterior.
- Semana inteira, de domingo a sábado, sem descanso.
- Sobreaviso acima de 24 horas na semana.
- Mês sem DSR.
- Dispensa (DISP) sem jornada ou em dia que não é feriado nem ponto facultativo.
- Férias: cada parcela deve ter de 5 a 30 dias seguidos, e a CH registrada no período deve ser igual à CH contratual do período (na 12x36, aceita até 12h de diferença; no plantão de 24h, exata). FE pode ser lançado sozinho em qualquer dia.
- Mesmo empregado com horários sobrepostos em duas escalas da unidade.
- Disponibilidade Alcançável fora da conversão: horas convertidas acima de 50% da CH, DA diferente de 3 vezes a conversão, ou DA em dia com jornada.

## Quadro de horas

| Coluna | O que mostra |
|---|---|
| CH Contratual | Horas que o empregado deve cumprir no mês, já descontados os feriados |
| CH Escala Regular | Horas das jornadas lançadas |
| CH Conversão DA | Horas da CH contratual convertidas em DA (cada 1h convertida = 3h de DA) |
| CH Escala DA | Tempo de DA lançado |
| CH Escala Regular e DA | Escala regular + 1/3 da DA |
| CH JE | Jornada Extraordinária (não entra no saldo) |
| CH Escala SA | Sobreaviso (não entra no saldo) |
| Saldo | Negativo: faltam horas na escala. Positivo: há horas a mais |

Exemplo: CH contratual de 100h com conversão de 50h → 50h de escala regular + 150h de DA = 100h, saldo 0.

Qualquer coluna pode ser ocultada pelo ícone do olho no cabeçalho e exibida de novo pelo menu **Exibir**.

## Várias escalas na mesma unidade

A unidade pode ter mais de uma escala (ex.: Enfermagem e Médicos). Escolha a escala na lista ao lado do mês; no botão **⋯** dá para criar, renomear, duplicar ou excluir escalas. O cadastro de empregados e os feriados são os mesmos para todas: em **Administração**, marque em **Nesta escala** quem entra na escala aberta. Cada escala tem seus próprios regimes (DA/SA), lançamentos e observações. Em **Exportar** há opções para gerar o arquivo do MentorH e as planilhas de todas as escalas de uma vez.

## Consulta e alteração

O botão **Alteração**/**Consulta**, no alto, trava a escala, o cadastro e os feriados para evitar mudanças por engano. Em modo consulta, qualquer tentativa de alterar pergunta se você quer liberar.

## Atenção: faça backup

Os dados ficam salvos **só no navegador do computador** onde a escala foi feita. Em outro computador ou navegador, a escala aparece vazia, e limpar os dados de navegação apaga tudo.

- Ao terminar, clique em **Backup › Salvar backup** e guarde o arquivo na pasta do setor.
- Para continuar em outro computador, clique em **Backup › Restaurar backup** e escolha esse arquivo. O sistema pergunta se o backup deve **substituir** os dados ou ser **acrescentado** como escala(s) nova(s).

## Dúvidas

A aba **Ajuda**, dentro do sistema, explica cada tela e cada regra. Problemas e sugestões de melhoria podem ser enviados à Coordenação-Geral de Documentação, Registro e Jornada de Trabalho.

---
Coordenação-Geral de Documentação, Registro e Jornada de Trabalho — HU Brasil
