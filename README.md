# Fatoração por Tentativas: Desvendando os Blocos de Construção dos Números (com um toque de Ironia)

Ah, fatoração... aquele processo matemático que parece tão simples, mas que pode te deixar coçando a cabeça quando os números ficam grandes. Mas não tema, jovem padawan da matemática, pois a **Divisão por Tentativas** está aqui para te salvar (ou pelo menos te entreter)!

## O que diabos são Fatores Primos?
Imagine que os números são como brinquedos de Lego. Números primos são aqueles blocos básicos, indivisíveis, que formam a base de tudo. Fatores primos, por sua vez, são a lista de blocos específicos que você precisa para construir um determinado brinquedo (ou número, nesse caso).

Por exemplo, o número 12 é como um carrinho Lego construído com os seguintes blocos primos: $$2, 2$$ e $$3$$ ($$2^2 \times 3$$).

## Divisão por Tentativas: A Arte de Tentar (e Acertar)
Este método é como um detetive testando suspeitos. Vamos dividindo o número por primos cada vez maiores e vendo se a divisão é exata. Se for, achamos um fator primo! Repetimos o processo com o quociente até sobrar apenas 1 ou um número primo.

## Passo a Passo com Código (porque exemplos são legais)
Vamos dissecar o código C++ que implementa a **Divisão por Tentativas** com um toque de humor:

```c++
#include 

vector<int> fatores_primos(int n) {
    vector<int> fatores; // Lista para armazenar os fatores primos descobertos

    // Caso especial: Se o número for 1, ele não tem fatores primos (é um solitário)
    if (n == 1) {
        return fatores; // Retornamos uma lista vazia
    }

    // Enquanto o número for par, dividimos por 2 (o primeiro primo) e adicionamos 2 à lista
    while (n % 2 == 0) {
        fatores.push_back(2);
        n /= 2;
    }

    // Agora, testamos a divisibilidade por números ímpares até a raiz quadrada de n
    for (int i = 3; i <= sqrt(n); i += 2) {
        while (n % i == 0) {
            fatores.push_back(i);
            n /= i;
        }
    }

    // Se sobrou algum número maior que 1, ele é um primo em si mesmo
    if (n > 1) {
        fatores.push_back(n);
    }

    // Voilá! Retornamos a lista dos fatores primos
    return fatores;
}
```
*Use code with caution.*

## Explicação Detalhada:
- **Inicialização**: Criamos um vetor `fatores` para armazenar os fatores primos encontrados.
- **Caso especial**: Se o número for 1, retornamos uma lista vazia, pois 1 não tem fatores primos.
- **Divisão por 2**: Enquanto o número for par, dividimos por 2 e adicionamos 2 à lista de fatores.
- **Divisão por ímpares**: Testamos a divisibilidade por números ímpares (começando com 3) até a raiz quadrada do número. Se a divisão for exata, adicionamos o fator à lista e dividimos o número por esse fator.
- **Primo restante**: Se sobrou algum número maior que 1 após as divisões, ele é um primo em si mesmo e o adicionamos à lista.
- **Retorno**: Finalmente, retornamos a lista de fatores primos encontrados.

**Lembre-se**:
- A **Divisão por Tentativas** não é o método mais eficiente para números gigantes, mas é um bom ponto de partida para entender a fatoração.
- Existem algoritmos mais avançados, como o Crivo de Eratóstenes e o método de Pollard Rho, para fatorar números grandes.
- Divirta-se fatorando! (ou pelo menos tente)
