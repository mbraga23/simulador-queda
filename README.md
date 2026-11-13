# Simulador de Queda de Tensão ⚡

Calculadora gratuita de queda de tensão para circuitos elétricos em baixa tensão, pensada para eletricistas, estudantes e profissionais de eletrotécnica.

**Aplicação online (após habilitar GitHub Pages):** https://mbraga23.github.io/simulador-queda/

## Recursos

- Potência em W ou kW, tensão, distância de ida, fator de potência e alimentação com 2 condutores ou trifásica equilibrada
- Exemplos de chuveiros, wallboxes, ar-condicionado e carregadores rápidos
- Cobre ou alumínio; seções de 1,5 a 240 mm²; temperatura do condutor ajustável
- Queda de tensão em volts e %, corrente, tensão estimada na carga e distância máxima por queda
- Limite de queda do circuito, queda anterior e limite global (5% ou 7%) separados
- Comparativo de seções: *critério de queda de tensão apenas*
- Gráfico, cópia de resumo, compartilhamento de cenário por URL e impressão
- Funciona sem instalar dependências ou servidor; cálculos realizados localmente no navegador

## Como usar

Abra `index.html` diretamente no navegador ou hospede na raiz do GitHub Pages. Modifique os dados ou escolha um dos exemplos. A distância é **somente a ida**, não a soma dos condutores.

## Metodologia (estimativa em regime permanente)

Corrente: `I = P/(V × FP)` (2 condutores) ou `I = P/(√3 × V × FP)` (trifásico equilibrado).

Queda de tensão aproximada:

- 2 condutores: `ΔV = 2 × I × (R × FP + X × senφ) × L/1000`
- Trifásico equilibrado: `ΔV = √3 × I × (R × FP + X × senφ) × L/1000`

`R` é resistência por km ajustada para a temperatura, `X` é reatância por km, `L` é distância de ida (m), `P` é potência **elétrica de entrada** (W), `V` é tensão do circuito e `FP=cosφ`. O modelo presume tensão nominal constante, condutores idênticos, carga equilibrada e regime permanente.

Valores de resistência de referência a 20 °C por seção conforme limites típicos da IEC 60228; corrigidos pela aproximação linear da temperatura. X padrão = 0,08 Ω/km quando não informado pelo fabricante, valor orientativo do *Electrical Installation Guide*, da Schneider Electric: https://www.electrical-installation.org/enwiki/Calculation_of_voltage_drop_in_steady_load_conditions

## Limites normativos: atenção

Pela ABNT NBR 5410:2004, item 6.2.7, o circuito **terminal não pode exceder 4%**. Na instalação usual atendida em BT a partir do ponto de entrega, o limite **total é de 5%**; em algumas configurações com transformador de MT/BT ou geração própria, **7%**. A verificação do circuito terminal **e** a verificação global devem ser feitas simultaneamente. Verifique a edição vigente e os detalhes aplicáveis ao projeto.

## Segurança e limitações

**Não é dimensionamento completo, laudo nem aprovação normativa.** A bitola calculada atende **somente à queda de tensão estimada**; pode ser insuficiente por ampacidade. Conferir método de instalação, isolação, temperatura ambiente, agrupamento, capacidade de condução, proteção contra sobrecarga/curto-circuito, contatos indiretos, seções mínimas, harmônicas, desequilíbrio, partidas de motores, fabricante, concessionária e demais requisitos. Para estações DC e circuitos de grande potência, confirme especialmente tensão real, dados de catálogo, cabos em paralelo, demanda e corrente de projeto.

Desenvolvido para uso educativo e pré-dimensionamento — **MS Elétrica & Tech**.
