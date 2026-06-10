# Largada BR - Requisitos

# Inputs
- botão ORÇA fechada (1/2/reset)
- botão BOIA largada (1/2/reset)
- botão CONTAGEM para largada (5min/1min/fim)
- botão COMPARAR desempenho (1/2)
- velocidade do GPS
- lat/long do GPS

# Outputs
- audio (autofalante bluetooth)
- log em arquivo texto
  
Nota: o termo "avisar" = emitir áudio + logar em arquivo

# Medições do GPS
A cada 5s o LBR deve calcular o rumo a partir das coordenadas: fórmula (considerando 10s de deslocamento)

A cada 5s o LBR deve indicar se houve perda ou ganho de velocidade com relação a TBD

# Calculo da direção do vento estimado

INFO: Como o sistema não possui sensor de direção do vento, este é estimado pela bissetriz dos ângulos que o veleiro faz em orça fechada com vela à direita e com vela à esquerda.

Se o botão ORÇA for pressionado e o rumo não for constante pelas últimas 2 medidas, LBR deve avisar "Manter rumo e tentar novamente".

Se o botão ORÇA for pressionado pela primeira vez e o rumo for constante pelas últimas 2 medidas, LBR deve armazenar o ângulo como o1 e avisar "Orça 1 definida como XXX" (XXX em ponto cardinal no audio e graus no log)

Se o botão ORÇA for pressionado após o1 definido e o rumo for constante pelas últimas 2 medidas, LBR deve armazenar o ângulo como o2 e avisar "Orça 2 definida como XXX" (XXX em ponto cardinal no audio e graus no log)

Quando o1 e o2 estiverem definidos, LBR deve calcular vento como a bissetriz entre o1 e o1 e alertar "Vento calculado como XXX" (XXX em ponto cardinal no audio e graus no log)

Se o botão ORÇA for pressionado e o1 e o2 já estiverem definidos, LBR deve resetar o1 e o2 e avisar "Reset do vento estimado".

Se o rumo for constante por 4 medidas dentro da zona morta com velocidade >2kt, LBR deve deslocar a zona morta e o vento pela quantidade de graus que o rumo estiver adentro, e alertar "Vento calculado como XXX" (XXX em ponto cardinal no audio e graus no log)

# Calculo da linha de largada

INFO: A linha virtual de largada é calculada a partir da marcação das duas boias, levando o veleiro até elas para definir as suas coordenadas.

TO DO: adicionar> Cálculo da posição da linha de largada

# Contagem regressiva para largada

Se o botão CONTAGEM for pressionado pela primeira vez, LBR deve 

Se o botão CONTAGEM for pressionado pela segunda vez, LBR deve 

TO DO: adicionar>
- Indicação do lado vantajoso para largar
- Contagem regressiva para largada
- Aviso de acelerar/reduzir velocidade no minuto final

# Comparação de desempenho

TO DO: adicionar> Comparação de desempenho em diferentes configurações

# Finalização da regata

Se o botão CONTAGEM for pressionado pela terceira vez, LBR deve registrar toda a trajetória acumulada em arquivo CSV contendo: tempo, coordenadas, rumo, velocidade, e avisar "Regata finalizada".
