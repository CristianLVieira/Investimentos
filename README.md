# Investimentos
Anotações de Aulas de Investimentos do MPE da EESP.

## Teoria de Gestão de Portfólios - Atualização
### Métricas de Retorno

A teoria de portfólios desenvolvida por: Markowitz (1952) dadas certas hipóteses, busca maximizar o retorno ajustado ao risco de um determinado portfólio.
Para tanto entre os assuntos analisados, veremos:

- As métricas usuais de risco e retorno utilizadas na construção de um portfólio;
- A elaboração de uma fronteira eficiente para um dado portfólio
- Algumas variações do modelo proposto por Markowitz
- As limitações e críticas mais relevantes a essa teoria
- Os conceitos de correlação e diversificação

Ao escolher um portfólio queremos selecionar portfólios que propiciem um retorno esperado interessante para um determinado nível de risco que estamos dispostos a assumir e para selecionar esses retorno precisamos definir:

- A métrica que utilizaremos para mensurá-los
- O método que utilizaremos para estimá-los

Temos duas métricas usuais no mercado para o cálculo desses retornos:

- Retorno simples
$$r_t = \frac{P_t - P_{t-1}}{P_{t-1}}\$$

- Retornos contínuos
$$g_t = ln {\left (\frac{P-t}{P_{t-1}} \right)}\$$

Qual das métricas é a mais adequada?

A resposta para essa pegunta não é trivial, pois:

- Para horizontes de investimento de longo prazo, retornos simples superestimam o retorno esperado
- Para horizontes de curto prazo, retornos contínuos subestimam o retorno esperado.

Adicionalmente:

O retorno simples acumulado do portfólio não corresponde a soma dos retornos simples do portfólio ao longo do período:

$$
 ln {\left(\frac{P_1}{P_0}\right)} +
 ln {\left(\frac{P_2}{P_1}\right)} +
 ln {\left(\frac{P_3}{P_2}\right)} + ... +
 ln {\left(\frac{P_T}{P_{T-1}}\right)} =
 ln {\left(\frac{P_T}{P_0}\right)}
$$

no entanto

$$
 \frac{P_1-P_0}{P_0} +
 \frac{P_2-P_1}{P_1} +
 \frac{P_3-P_2}{P_2} + ... +
 \frac{P_T-P_{T-1}}{P_{T-1}} \neq
 \frac{P_T-P_0}{P_0}
$$

O retorno contínuo do portfólio em um dado período não corresponde a média ponderada dos retornos contínuos dos seus ativos:

$$ [r_p = \sum\limits_{i=1}^{N}{\omega_ir_i}\] $$

mas

$$ [g_p = ln(1 + r_p) = ln(1 + \sum\limits_{i=1}^{N}{\omega_ir_i}) \neq \sum\limits_{i=1}^{N}{\omega_ig_i}\] $$

Se assumirmos que os retornos contínuos sejam invariantes no tempo (i.e., i.i.d.) e normais, podemos estimar o retorno esperado projetando o retorno de um período ao longo de k períodos.
Entretanto, se os retornos contínuos apresentarem uma distribuição normal, por construção os retornos simples $r_t + 1$ apresentarão uma distribuição lognormal pois $g_t = ln(r_t + 1)$.
As análises das séries de tempo de retornos empregam retornos contínuos para avaliar os instrumentos individualmente.
Posteriormente, esses retornos são convertidos em retornos simples para que possam ser utilizados na análise da performance de um portfólio.
Obviamente, caso os retornos não tenham distribuição normal ou não sejam i.i.d. (e.g., heterocedasticidade, correlação serial, assimetria), estruturas adicionais devem ser incorporadas à análise das séries de tempo.
