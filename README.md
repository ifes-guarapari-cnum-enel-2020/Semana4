# Semana4
![](https://github.com/ifes-guarapari-cnum-enel-2020/Semana4/workflows/Julia%20CI/badge.svg)

Atividades Pedagógicas Não Presenciais

## Erro com pontos flutuantes
Em sistemas digitais, os números reais são representados de forma discreta, não exata, dado o limitante de memória finita para operações de armazenamento e processamento. Tal fato ocasiona erros de cálculo, que devem ser considerados nas soluções algorítmicas.

https://www.ufrgs.br/reamat/CalculoNumerico/livro-py/rdneadm.html

Nesse exercício, o objetivo é identificar a quantidade de somas capaz de serem realizadas por uma máquina em Julia, de modo a calcular o exponencial do número de Euler, por série de Taylor.
```julia
function e(x)
 termo = 1
 soma = 1
 n = 1
 while termo > 0
  termo = termo * (x/n)
  soma = soma + termo
  n = n + 1
 end
 return [soma n]
end

y = e(1)
println(y[1])
println(y[2])

y = e(2)
println(y[1])
println(y[2])
```

Observa-se na solução que os termos das somas da série de Taylor diminui a cada divisão, até a capacidade de Underflow da máquina, encerrando o loop ao chegar no valor de zero.
