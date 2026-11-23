# Escala Mensal de Trabalho — HU Brasil

Ferramenta para elaborar, conferir e exportar a **escala mensal de trabalho** das equipes do HU Brasil. Há duas versões que seguem as mesmas regras: um sistema em HTML que funciona offline e planilhas Excel alternativas.

## Sistema HTML (`index.html`)

É um arquivo único, que roda direto no navegador. Não precisa de instalação nem de internet, e os dados ficam salvos no próprio navegador (localStorage).

- **Escala:** a grade mensal tem lançamento por clique ou digitação, sugestões de jornadas e afastamentos, combinação de jornada com afastamento (`MT22 AT`, `D12+FE`), copiar/colar e desfazer/refazer.
- **Quadro de carga horária:** CH Contratual, CH Conversão DA (quando há DA), CH Escala Regular, CH JE (opcional), CH Escala DA, CH Escala SA, CH Escala Regular, DA e SA e Saldo.
- **Inconsistências:** o sistema aponta
  - 7 ou mais dias consecutivos de trabalho, contando o mês anterior;
  - Sobreaviso acima de 24h por semana (domingo a sábado);
  - mês sem DSR;
  - Dispensa sem jornada ou em dia que não é feriado nem ponto facultativo;
  - mês com férias em que a escala não fecha a CH contratual (na 12x36, tolera até 12h de diferença).
  - Disponibilidade Alcançável fora da conversão contratual: CH convertida acima de 50%, DA escalada diferente de 3 vezes a conversão do mês, presencial + DA/3 acima da CH contratual e DA em dia com jornada regular.
- **Administração:** cadastro de empregados com matrícula, cargo, especialidade, CH, vínculo, CH semanal convertida em DA (até 50%, 1h = 3h de DA) e indicação de regime de SA.
- **Feriados:** feriados e pontos facultativos por lotação.
- **Códigos e legenda:** jornadas do POP.DGP.042, Sobreaviso (POP.DGP.039), Disponibilidade Alcançável (POP.DGP.108) e afastamentos padronizados conforme o MentorH.
- **Exportação:**
  - Excel com fórmulas, do ano inteiro ou de um mês só;
  - arquivo TXT de importação para o MentorH;
  - impressão em A4 paisagem.
- **Backup:** exportação e restauração dos dados em arquivo.
- **Ajuda:** guia de uso com as regras de JE, SA, DA e Dispensa.

## Planilhas Excel alternativas

Têm o mesmo layout do sistema, com fórmulas protegidas, formatação condicional por código e legenda. Existem em 4 variantes:

| Variante | Conteúdo |
|---|---|
| 1_Regular | Escala regular |
| 2_Regular_DA_SA | Regular + Disponibilidade Alcançável + Sobreaviso |
| 3_Regular_DA | Regular + Disponibilidade Alcançável |
| 4_Regular_SA | Regular + Sobreaviso |

Cada variante tem a versão de **2027** (ano inteiro) e a de **Dezembro/2026**.

## Paleta de cores

- **Jornadas:** tons derivados da identidade visual HU Brasil.
- **Afastamentos:** cada código tem uma cor única, e famílias parecidas usam tons próximos (por exemplo, MP e 2MP).

## Estrutura do projeto

| Caminho | Função |
|---|---|
| `app/core.js` | Regras de negócio: interpretação de códigos, cálculo de horas, inconsistências e cores |
| `app/data_v7.json` | Jornadas, afastamentos, cargos e paleta |
| `app/template_v11.html` | Interface |
| `app/build_v13.py` | Gera o HTML final (arquivo único) |
| `scripts/build_alt.py` | Gera as planilhas alternativas (xlsxwriter) |
| `scripts/pack_tpl.py` | Empacota o modelo de planilha que o HTML usa na exportação |

```bash
# Planilhas
python3 scripts/build_alt.py SAIDA.xlsx REG_DA_SA            # 2027
python3 scripts/build_alt.py SAIDA.xlsx REG --ano 2026 --so-dez

# HTML
python3 scripts/pack_tpl.py
python3 app/build_v13.py
```

## Testes

- Recálculo das planilhas no LibreOffice.
- Testes de interface com Playwright.
- Comparação, valor a valor, entre a planilha exportada e o `core.js` (0 divergências).

---
Coordenação-Geral de Documentação, Registro e Jornada de Trabalho — HU Brasil
