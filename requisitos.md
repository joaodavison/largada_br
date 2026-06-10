# Largada BR

# Inputs
- botão orça fechada (1/2/reset)
- botão boia largada (1/2/reset)
- botão largada (5min/1min/reset)
- velocidade do GPS
- lat/long do GPS

# Outputs
- audio (autofalante bluetooth)
- log em arquivo texto
Nota: o termo "avisar" = emitir áudio + logar em arquivo

# Medições
A cada 5s o LBR deve calcular o rumo a partir das coordenadas: fórmula

A cada 5s o LBR deve indicar se houve perda ou ganho de velocidade com relação a TBD

# Calculo da direção do vento estimado

Se o botão orça for pressionado e o rumo não for constante pelas últimas 2 medidas, LBR deve avisar "Manter rumo e tentar novamente".

Se o botão orça for pressionado pela primeira vez e o rumo for constante pelas últimas 2 medidas, LBR deve armazenar o ângulo como o1 e avisar "Orça 1 definida como XXX" (XXX em ponto cardinal)

Se o botão orça for pressionado após o1 definido e o rumo for constante pelas últimas 2 medidas, LBR deve armazenar o ângulo como o2 e avisar "Orça 2 definida como XXX" (XXX em ponto cardinal)

Quando o1 e o2 estiverem definidos, LBR deve calcular vento como a bissetriz entre o1 e o1 e alertar "Vento calculado como XXX" (XXX em ponto cardinal)

Se o botão orça for pressionado e o1 e o2 estiverem definidos, LBR deve resetar o1 e o2 e avisar "Reset das orças".

Se o rumo for constante por 4 medidas dentro da zona morta com velocidade >2kt, LBR deve deslocar a zona morta e o vento pela quantidade de graus que o rumo estiver adentro e alertar "Vento calculado como XXX" (XXX em ponto cardinal)

# Calculo da linha de largada

# Contagem regressiva para largada

# Finalização da regata

