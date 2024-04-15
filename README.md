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

### Exemplo

Série de retornos contínuos diários de um dado ativo seja normal e i.i.d. tal que:

$$ [g_t \sim N(\mu_d, \sigma_d^2)\] $$

Lembrando que para retornos i.i.d.:

$$ [Var(g_t + g_{t+1}) = Var(g_t) + Var(g_{t+1}) + 2Cov(g_t,g_{t+1})\] $$

$$ [Var(g_t + g_{t+1}) = Var(g_t) + Var(g_{t+1})\] $$

Podemos projetar o retorno contínuo semanal (5 dias úteis) por:

$$ [g_t \sim N(5\mu_d, 5\sigma_d^2)\] $$

De modo que

$$ [{\mu_s = 5\mu_s} e\ {\sigma_s = \sqrt{5\mu_d}}\] $$

Em seguida, simulamos 10.000 retornos aleatórios com distribuição $N(5\mu_d,5\sigma_d^2)$ e convertemos esses retornos contínuos em retornos simples utilizando:

$$ [r_k=e^{g_k} -1\] $$

Posteriormente, repetimos esse procedimento para outros $N-1$ ativos similares (i.i.d. e normalmente distribuídos).

Finalmente, utilizando os retornos simples aleatórios gerados para os N ativos, calculamos os retornos semanais simulados do portfolio (por exemplo, assumindo alocações idênticas ou equal weight).

$$ [r_p=\sum\limits_{i=1}^{N}{\omega_ir_i}\] $$

Em nossa análise não consideramos outros elementos importantes como expectativas de inflação ou impactos tributários que são comuns em aplicações práticas.

Até agora discutimos somente a métrica, apenas a definição da forma de capitalização dos retornos (simples ou contínua), e isso não é suficiente para realizarmos análises adequadas.

Também são necessárias padronizações para facilitar a comparação de diferentes horizontes de investimento.

### Exemplo
 
Suponha um horizonte de investimento de $k = 3$ anos e um retorno efetivo simples (i.e. um linear holding period return) de 40\%.

Nesse exemplo temos:

- Holding Period Return (HPR)
$$ [HPR = 40\%\] $$

- Effective Annual Rate (EAR)
$$ [HPR = (EAR+1)^{k}-1 \Longrightarrow EAR = (1+HPR)^\frac{1}{k} \Longrightarrow EAR=(1+0,4)^\frac{1}{3} \Longrightarrow EAR=11,9\%\] $$

- Annual Percentage Rate (APR)
$$ [APR=HPR \frac{1}{k}-1 \Longrightarrow \frac{(EAR+1)^k-1}{k} \Longrightarrow \frac{(0,119+1)^3-1}{3} \Longrightarrow APR = 13,3\%\] $$

- Continuous Compounded Rate (CCR)
$$ [EAR=e^{CCR}-1 \Longrightarrow CCR = ln(EAR+1) \Longrightarrow CCR = 11,2\%\] $$

Note ainda que, quando nos referimos a retornos auferidos (e não a retornos esperados), outras métricas de retorno são comuns:

- Compounded Annual Growth Rate (CAGR)
- Internal Rate of Return (IRR)
- Return on Investment (ROI)

É importante lembrar que quando analisamos retornos esperados, estamos em geral nos referindo a retornos em excesso (ou excess return) em relação a uma determinada taxa livre risco (i.e., o custo de oportunidade).

O valor esperado desses retornos em excesso são denominados prêmios de risco (ou risk premia) que, como veremos posteriormente, são elementos essenciais na elaboração de bons portfólios de investimentos.
