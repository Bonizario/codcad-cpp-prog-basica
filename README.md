<p align="center">
  <img src="./assets/logo.png" />
</p>

<br>

<h2 align="center">Anotações e soluções dos exercícios do curso "Programação Básica para Competições de Programação (em C++) - CodCad"</h2>

<h3 align="center">Todas as videoaulas e exercícios podem ser acessados na plataforma <a href="https://neps.academy/course/6" target="_blank" style="color:#32cd32;">Neps Academy</a></h3>

<br>
<h3 align="center">
<a href="#introducao" style="color:#32cd32;">Introdução</a>
 | <a href="#controle" style="color:#32cd32;">Controlando o Código</a>
 | <a href="#vetoresematrizes" style="color:#32cd32;">Vetores e Matrizes</a>

<a href="#cadeiadecaracteres" style="color:#32cd32;">Cadeia de Caracteres</a>
| <a href="#funcoeseordenacao" style="color:#32cd32;">Funções e Ordenação</a>

</h3>

<br>
<h1 id="introducao">:green_book: Introdução</h1>

Usaremos a linguagem de programação C++ e a IDE Code::Blocks.

Uma linguagem de programação é um método padronizado, formado por um conjunto de regras sintáticas e semânticas, de implementação de um código fonte - que pode ser compilado e transformado em um programa de computador, ou usado como script interpretado - que informará instruções de processamento ao computador.

Uma IDE é um programa que facilita a criação de programas. Podemos compilar e executar o código diretamente no ambiente da IDE e também detectar erros de escrita com ferramentas de debug.

Arquivos em C++ possuem a extensão **.cpp**.

_**Nota**_: **F9: compila + executa, Ctrl + F9: compila, Ctrl + F10: executa**

<br>
<h2>Introdução</h2>

A função `main()` é a primeira coisa que o computador vai procurar ao executar o programa.

Podemos imprimir mensagens na tela com a função `cout` da biblioteca `iostream`.

Os caracteres impressos devem estar entre aspas duplas `""` e, caso deseje imprimir mais de uma mensagem, elas ficarão separadas por dois sinais de menor `<<`.

_Comentários de código são feitos com barras duplas_ `//` _(uma linha), ou então_ `/* */` _(em bloco)._

_Comentários não são lidos pelo compilador e ajudam no entendimento do leitor._

```cpp
#include <iostream> // declarando as bibliotecas usadas

using namespace std;

int main() { // declarando a função main, o "corpo" do programa

  cout << "mensagem 1" << "mensagem 2" << "..." << "\n";

  return 0; // informando ao sistema operacional que o programa terminou
}

```

A maioria dos comandos precisam terminar com um ponto e vírgula `;`.

`"\n"` ou `endl` é um caractere de escape usado para fazer a quebra de linha, igual quando apertamos a tecla enter.

Símbolos:

- Atribuição: `=`
- Adição: `+`
- Subtração: `-`
- Multiplicação: `*`
- Divisão: `/`
- Resto: `%`

<br>
<h2>Entrada e Saída</h2>

Um programa pode ser dividido em três etapas: entrada, processamento e saída.

Variáveis são endereços de memória utilizados para armazenar e manipular valores. No programa, uma variável é acessada por meio de um nome especificado na sua declaração.

Em C++ existem três tipos básicos de variável:

- _int_: inteiro
- _float/double_: real
- _char_: caractere

Para armazenarmos um input em uma variável, podemos usar `cin`. As variáveis são separadas por sinais de maior `>>`.

`cout.precision()` delimita quantas casas decimais serão impressas (_float/double_).

```cpp
#include <iostream>

using namespace std;

int main() {
  double raio; // declarando a variável raio

  cin >> raio; // lendo o valor na tela e salvando em "raio"

  double pi = 3.14159; // declarando a variável pi e seu valor simultaneamente

  cout.precision(2); // indicando a precisão do número que vai ser impresso
  cout.setf(ios::fixed);

  cout << "A area eh " << raio * raio * pi << "\n"; // imprimindo a frase "A area eh " seguida do valor da área com 2 casas e quebra de linha

  return 0;
}
```

Cada tipo de variável possui um <a href="http://www.cplusplus.com/reference/climits/" target="_blank" style="color:#32cd32;">limite de armazenamento</a> específico.

Por exemplo, _int_: -32767 a 32767 e _long int_: -2147483647 a 2147483647.

<br>
<h2>Principais erros</h2>

- Ponto e Vírgula: `expected ';' before 'return'`

- Variável não declarada: `'X' was not declared in this scope`

- Erros sintaxe/lógicos: `A+B/2` ao invés de `(A+B)/2`

É importante ler a mensagem do erro e tentar descobrir o que o ocasionou.

Uma técnica simples e muito útil para encontrar a origem dos erros é imprimir as váriaveis múltiplas vezes ao longo do código. Caso elas apresentem valores corretos, o erro provavelmente está em outra parte do programa.

<br>
<h1 id="controle">:green_book: Controlando o Código</h1>

<h2>Seleção - Parte 1</h2>

O _if_ é uma estrutura de controle que permite executar uma sequência de comandos se uma dada condição for verdadeira.

`if (condição) { comandos }`

Operadores para montarmos condições:

- `x == y`: x é igual a y
- `x != y`: x é diferente de y
- `x >= y`: x é maior ou igual a y
- `x <= y`: x é menor ou igual a y
- `x > y`: x é maior que y
- `x < y`: x é menor que y

_Note que usamos **2** símbolos de igualdade para **comparar** valores, **1** igual é símbolo de **atribuição**._

É possível combinar condições com os operadores lógicos **and** (**&&**) e **or** (**||**):

- condição 1 _**and**_ condição 2 **&&** condição 3: todas as condições precisam ser verdadeiras
- condição 1 _**or**_ condição 2 **||** condição 3: basta uma condição ser verdadeira

O `else` é usado quando a condição anterior em `if` não é satisfeita.

_se (if) a condição for verdade, faça isso; se não (else), faça isso_

<br>
<h2>Seleção - Parte 2</h2>

Podemos incluir uma condição no else, resultando em estruturas de if e else _aninhadas_.

`else if (condição) { comandos }`

```cpp
#include <iostream>

using namespace std;

int main() {
  double altura; // declarando a variável altura

  cin >> altura; // lendo o valor na tela e salvando em "altura"

  if (altura > 1.80) {
    cout << "Alta\n"; // A pessoa é considerada Alta
  }
  else if (altura > 1.5) {
    cout << "Media\n"; // A pessoa é considerada Media
  }
  else {
    cout << "Baixa\n"; // A pessoa é considerada Baixa
  }

  return 0;
}
```

<br>
<h2>Organização de Código</h2>

O compilador (programa que transforma seu código em linguagem de máquina) não interpreta linhas em branco, indentações ou espaços em branco em geral.

```cpp
#include <iostream>
using namespace std;
int main(){int x;cin>>x;if(x>0 and x%2==0){cout<<"x positivo e par\n";}
else{if(x<=0){cout<<"x nao positivo\n";}if(x%2!=0){cout<<"x nao par\n";}}return 0;}
```

O código acima não está errado, porém é muito difícil de ler e identificar eventuais erros.

_Indentação_ é o processo de adicionar tabulações (tecla _tab_) nos blocos de código de funções, ifs, for, while, etc. Tornando o código mais limpo, legível e bem estruturado.

Também são boas práticas pular uma linha após a declaração das biliotecas e `using namespace std`, deixar um espaço em branco entre os valores e operadores, entre os parênteses e chaves, etc.

```cpp
#include <iostream>

using namespace std;

int main() {
    int x; // primeiro nível de indentação
    cin >> x;
    if (x > 0 and x % 2 == 0) {
        cout << "x positivo e par\n"; // segundo nível de indentação
    } else {
        if (x <= 0) {
            cout << "x nao positivo\n"; // terceiro nível de indentação
        }
        if (x % 2 != 0) {
            cout << "x nao par\n";
        }
    }
    return 0;
}
```

<br>
<h2>Repetição (While)</h2>

Enquanto uma dada condição for verdadeira, o `while` executará os comandos dados.

Esse tipo de estrutura de repetição é muito útil quando não se conhece quantas repetições serão necessárias para obter-se o resultado desejado.

`while (condição) { comandos }`

_É importante tomar muito cuidado ao usar while, pois se o estado da condição nunca se tornar **falso**, o programa ficará em um **loop infinito**!_

```cpp
#include <iostream>

using namespace std;

int main() {
  int A; // declarando as variáveis A e B
  int B;

  cin >> A >> B; // lendo e armazenando os valores de A e B

  int i = A; // criando uma variável contadora i que começa de A

  while (i <= B) { // enquanto i for menor ou igual a B

    if (i % 2 == 0) { // se i é par
      cout << i << " "; // imprime i na tela
    }

    i = i + 1; // incrementando i
  }
  cout << "\n";

  return 0;
}
```

<br>
<h2>Repetição (For)</h2>

O `for` é muito usado para tarefas com um número de repetições definido, como por exemplo, percorrer os elementos de um vetor.

`for (inicialização; condição de parada; incremento) { comandos }`

Existem alguns operadores muito usados nesse tipo de estrutura:

- `x += y` equivale a `x = x + y`
- `x -= y` equivale a `x = x - y`
- `x++` equivale a `x = x + 1`
- `x--` equivale a `x = x - 1`

Algumas vezes, queremos parar a execução do for antes do seu critério de parada original, ou seja, o for terá seu critério de parada original, mas se outra condição dentro do for for verdadeira queremos que ele acabe. Para isso, usamos o comando `break`.

_`break` serve para parar qualquer loop, portanto ele funciona exatamente da mesma maneira no `while`._

```cpp
#include <iostream>

using namespace std;

int main() {
    int var;
    for (int i = 1; i <= 10; i++) { // repetindo uma sequência de comandos 10 vezes
        cin >> var; // lendo um valor e armazenando-o em var

        if (var == 0) { // se o valor for igual a 0
            break; // encerre o for
        }
        cout << 2 * var << "\n";
    }
    return 0;
}
```

`continue` ignora todos os comandos que o loop ainda deveria fazer na iteração atual e passa para a próxima iteração.

_`continue` **não** para o loop. Também funciona no `while`._

```cpp
#include <iostream>

using namespace std;

int main() {
    for (int i = 1;i <= 100; i++) { // repetindo uma sequência de comandos 100 vezes
        if (i % 7 == 0) { // se o resto da divisão de i por 7 for igual a 0
            continue; // siga para a próxima iteração
        }
        // todos os outros comandos que seriam executados após o continue são ignorados
        cout << i << " ";
    }
    cout << "\n";

    return 0;
}
```

Na prática, `break` e `continue` quase sempre estarão dentro de estruturas condicionais (_if, else_).

<br>
<h2>Matemática</h2>

Outra biblioteca muito útil na resolução de problemas é a `cmath`. Ela possui diversas funções e estruturas matemáticas prontas, facilitando o desenvolvimento.

Operações básicas:

- `pow(x, y)`: x elevado à y (_podemos obter a y-ésima raiz de x com `pow(x, 1.0 / y)`_)
- `sqrt(x)`: raiz quadrada de x
- `abs(x)`: valor absoluto de x
- `floor(x)`: arredonda x para baixo
- `ceil(x)`: arredonda x para cima

Trigonometria:

- `sin(x)`: seno de x
- `cos(x)`: cosseno de x
- `tan(x)`: tangente de x
- `asin(x)`: arco seno de x
- `acos(x)`: arco cosseno de x
- `atan(x)`: arco tangente de x

Logaritmo:

- `log(x)`: log na base _**e**_ de x
- `log10(x)`: log na base _**10**_ de x
- `exp(x)`: _**e**_ elevado à x

<br>
<h1 id="vetoresematrizes">:green_book: Vetores e Matrizes</h1>

<h2>Vetores</h2>

Um vetor em C++ pode ser entendido como um conjunto ordenado de variáveis _de um mesmo tipo_.

Podemos inicializar um vetor vazio ou preenchido de valores:

- `tipo_das_variaveis nome[n];`
- `tipo_das_variaveis nome[n] = {valor 1, valor 2, ..., valor n};`

É comum precisarmos inicializar um vetor completamente preenchido por zeros:

- `int nome[n] = {0};`

Todos os valores de um vetor se encontram em _índices_, o primeiro elemento está no _índice 0_, o segundo no _índice 1_ e assim por diante.

Para atribuir/modificar o valor no _índice n_ dentro de um vetor previamente declarado:

- `nome[n] = valor;`

Frequentemente precisamos percorrer todas as posições de um vetor por meio do `for`.

```cpp
#include <iostream>

using namespace std;

int main() {
  int n; // declarando a variável n (1 <= n <= 10^6)

  int sequencia[1000000]; // declarando um vetor de inteiros de 1000000 posições

  cin >> n; // lendo o valor na tela e atribuindo-o à n

  for (int i = 0; i < n; i++) {
    cin >> sequencia[i]; // salvando cada número em uma posição do vetor, de 0 até n - 1
  }

  for (int i = n - 1; i >= 0; i--) {
    cout << sequencia[i] << " "; // percorrendo o vetor de trás para frente, imprimindo seus elementos
  }
  cout << "\n"; // imprimindo a quebra de linha no fim do código

  return 0;
}
```

<br>
<h2>Matrizes</h2>

Basicamente, matrizes são vetores de duas dimensões. Portanto, o processo de inicializar uma matriz de _n linhas_ e _m colunas_ é bem semelhante ao dos vetores:

- `tipo_das_variaveis nome[n][m];`

Para atribuir/modificar um valor na linha _i_ e coluna _j_:

- `nome[i][j] = valor;`

É intuitivo pensar em preencher a matriz com alguma estrutura de repetição, e, nesse caso, usaremos dois laços `for` aninhados.

```cpp
#include <iostream>

using namespace std;

int main() {
    int n, m;
    int A[110][110], B[110][110]; // declarando duas matrizes 110x110
    cin >> n >> m;

    for (int i = 0; i < n; i++) { // para cada linha
        for (int j = 0; j < m; j++) { // para cada coluna
            cin >> A[i][j]; // leia um elemento e armazene-o na matriz A
        }
    }
    for (int i = 0; i < n; i++) { // para cada linha
        for (int j = 0; j < m; j++) { // para cada coluna
            cin >> B[i][j]; // leia um elemento e armazene-o na matriz B
        }
    }
    for (int i = 0; i < n; i++) { // para cada linha
        for (int j = 0; j < m; j++) { // para cada coluna
            cout << A[i][j] + B[i][j] << " "; // imprima a soma de  aij + bij
        }
        cout << "\n";
    }
    return 0;
}
```

<br>
<h1 id="cadeiadecaracteres">:green_book: Cadeia de Caracteres</h1>

<br>
<h2>Caracteres</h2>

Os caracteres que digitamos estão associados a _códigos_ da tabela <a href="https://pt.wikipedia.org/wiki/ASCII" target="_blank" style="color:#32cd32;">ASCII</a>.

Em C++, podemos armazenar um caractere em uma variável do tipo `char` _(o inteiro da tabela ASCII é armazenado)_.

É importante sempre usar _**aspas simples!**_

Para mostrar o código de um caractere, mudamos o tipo da variável de `char` para `int` com uma operação chamada _cast_:

```cpp
cout << (int)variavel_do_tipo_char << endl;
```

Verificando se a letra é maiúscula/minúscula:

```cpp
if (letra >= 'a' and letra <= 'z') { /* minúscula */ }
if (letra >= 'A' and letra <= 'Z') { /* maiúscula */ }
```

- `toupper()` e `tolower()` retornam char maiúsculo/minúsculo se existir
- `isupper()` e `islower()` verificam se o char é maiúsculo/minúsculo
- `isspace()` retorna valor não nulo se o char for ' ', '\f', '\n', '\r', '\t' ou '\v'.

<br>
<h2>Strings</h2>

`string` é um tipo de dado assim como `int` e `double`, mas que armazena uma cadeia de caracteres. Grande parte dos operadores comuns aos outros tipos também funciona com `string`:

- `string A;` - Declarando uma string
- `A = "frase para a variável";` - Atribuindo uma frase à string
- `cin >> A;` - Lendo uma palavra
- `getline(cin, A);` - Lendo uma linha completa
- `A += "outra frase";` - Adicionando uma frase ao final de uma string
- `A.size();` - Tamanho de uma string
- `A[i] == 'j'` - Compara o caractere que está no índice _i_ com o caractere _j_

É importante sempre usar _**aspas duplas!**_ Aspas simples são destinadas aos caracteres, variáveis do tipo `char`.

```cpp
#include <iostream>

using namespace std;

int main() {
    string nome; // inicializando a string nome

    int a = 0, i = 0, e = 0, o = 0, u = 0;

    getline(cin, nome); // lendo o nome digitado pelo usuário

    for (int j = 0; j < nome.size(); j++) { // percorrendo cada caractere de "nome"
        if (nome[j] == 'a') { // sempre aspas simples para char
            a++;
        } else if (nome[j] == 'e') {
            e++;
        } else if (nome[j] == 'i') {
            i++;
        } else if (nome[j] == 'o') {
            o++;
        } else if (nome[j] == 'u') {
            u++;
        }
    }
    cout << "a = " << a << endl;
    cout << "e = " << e << endl;
    cout << "i = " << i << endl;
    cout << "o = " << o << endl;
    cout << "u = " << u << endl;

    return 0;
}
```

<br>
<h1 id="funcoeseordenacao">:green_book: Funções e Ordenação</h1>

<h2>Funções</h2>

Em vários exercícios mais complexos é vantajoso estruturamos a lógica por meio de funções. Assim, nós componentizamos blocos de códigos que podem ser usados várias vezes ao longo do programa.

A sintaxe geral de uma função é:

```cpp
tipo_do_retorno nome(tipo_do_argumento argumento) {
    // lógica
    return retorno;
}
```

Chamamos uma função criada por nós mesmos da mesma forma que invocamos uma função padrão de alguma biblioteca.

Uma função pode ter vários parâmetros e eles podem receber qualquer nome (desde que seja válido para uma variável). A seguir, uma função que calcula a média de 3 `doubles`:

```cpp
#include <iostream>

using namespace std;

double media(double x, double y, double z) {
    int retorno = (x + y + z) / 3.0;
    return retorno;
}
```

Vale ressaltar que uma função pode ter um tipo de retorno diferente dos tipos dos seus parâmetros:

```cpp
#include <iostream>

using namespace std;

int count_a(string s) { // recebendo parâmetro do tipo string
  int n_a = 0;
  for (int i = 0; i < s.size(); i++) {
      if (s[i] == 'a') {
          n_a++;
      }
  }
  return n_a; // retornando o número de letras 'a' contidas em "s" (tem tipo int)
}
```

Além disso, uma função pode ter argumentos de tipos distintos:

```cpp
#include <iostream>

using namespace std;

string multiply_string(string s, int a) { // recebendo parâmetros de diferentes tipos
    string ss = "";
    for (int i = 0; i < a; i++) {
        ss += s;
    }
    return ss; // retornando a string s 'a' vezes seguidas
}
```

Um outro tipo de função, é a função do tipo `void`. Ela não retorna nenhum valor, geralmente só serve para modificar variáveis globais, que são declaradas fora de quaisquer funções, ou variáveis passadas por <a href="https://pt.wikibooks.org/wiki/Programar_em_C%2B%2B/Refer%C3%AAncias_de_dados" target="_blank" style="color:#32cd32;">_referência_</a>.

_Em especial, uma função só pode modificar variáveis globais que forem declaradas antes de si mesma._

```cpp
#include <iostream>

using namespace std;

string s = "Sou uma variável global";
void emptyness() {
    s = "Stare into the void."; // modificando string global s
    return;
}
```

<br>
<h2>Funções Recursivas</h2>

> Uma função recursiva é uma função que se refere a si própria. A ideia consiste em utilizar a própria função que estamos a definir na sua definição.

> Para funcionar, uma função recursiva precisa de um passo básico (ou mais) cujo resultado é imediatamente conhecido e um passo recursivo em que se tenta resolver um sub-problema do problema inicial.

A seguir, um exemplo que retorna o n-ésimo número de Fibonacci:

```cpp
#include <iostream>

using namespace std;

int fib(int n) {
    if (n < 2) { // casos de base, F(1) e F(0)
        return 1;
    }
    return fib(n - 1) + fib(n - 2); // funciona para os demais casos
}

int main() {
    int n;
    cin >> n;
    cout << fib(n) << "\n";
    return 0;
}
```

É importante tomar cuidado na escolha do caso base, o ideal é escolher o menor valor possível. Poderíamos escolher um caso base arbitrário como F(8).

Para valores maiores que 8 a função funcionaria perfeitamente. Contudo, para valores menores, o passo recursivo entraria em loop tendendo a -infinito!

<br>
<h2>Ordenação - Parte 1</h2>

Existem várias técnicas e algoritmos que nos permitem ordenar um array. 

O código a seguir demonstra o algoritmo _Selection Sort_. Basicamente ele seleciona o menor número do vetor, imprime e salva o seu índice. Assim, nas próximas repetições esse número não voltará a ser impresso.

```cpp
for (int i = 1; i <= n;i++) { // para cada número a ser impresso
  
  menor = INF; // fazemos menor começar como infinito, ou seja, um número muito grande
  
  for (int j = 1; j <= n; j++) { // percorrendo o vetor
    
    if (lista[j] == 0 && vetor[j] < menor) { // procurando um número menor que "menor" que não esteja na lista
      
      menor = vetor[j]; // fazemos "menor" receber seu valor
      ind_menor = j; // guardamos seu índice em "ind_menor"
    }
  }
  
  cout << menor << " "; // imprimindo o menor número que achamos
  
  lista[ind_menor] = 1; // guardando seu índice na lista de impresos
}
```
Em sequência, está o _Bubble Sort_. Nele, percorremos o vetor várias vezes, invertendo os números desordenados. Ele se encerra quando o vetor estiver completamente ordenado.
```cpp
int ordenado = 0; // inicializando "ordenado" como 0, para que o loop comece
   
while(ordenado == 0){ // enquanto ordenado for 0
     
  ordenado = 1; // supomos que o vetor está ordenado
     
  for(int i=1; i < n; i++){ // para todas as posições, exceto a última
    if(vetor[i] > vetor[i+1]){ // checamos se há inversão entre vetor[i] e vetor[i + 1]
        
      // se houver, trocamos os valores de vetor[i] e vetor[i+1]
      int tmp = vetor[i];
      vetor[i] = vetor[i+1];
      vetor[i+1] = tmp;
        
      ordenado = 0; // salvamos que o vetor não está ordenado
    }
  }
}
```

Vale notar que ambos os algoritmos acima não são rápidos. Para vetores grandes, geralmente maiores que 10^4, é necessário usar métodos mais sofisticados.

A biblioteca `<algorithm>` possui uma função `sort()` que nos permite ordenar um vetor do menor ao maior:

- `sort(inicio, fim)` 

`inicio` é um ponteiro para a primeira posição que queremos ordenar e `fim` um ponteiro para a primeira posição que não queremos ordenar. Assim, para ordenarmos um vetor `v` de tamanho `n`, usamos o comando `sort(v, v + n)`. _(O vetor é indexado de **0** a **n - 1**, o index **n** não existe!)_

```cpp
#include <iostream>
#include <algorithm> // biblioteca que contém a função sort

using namespace std;

int main(){
  int N;
  cin >> N;
  int v[N];

  for (int i = 0; i < N; i++) {
    cin >> v[i]; // armazenando as variáveis do vetor
  } 

  sort(v, v + N); // ordenando as N posições do vetor

  for (int i = 0; i < N; i++) {
    cout << v[i] << " "; // imprimindo cada posição
  }

  cout << "\n";
  return 0;
}
```

<br>
<h2>Ordenação - Parte 2</h2>

A função `sort()` possui um terceiro parâmetro, uma função opicional. Por meio dela, poderemos personalizar os critérios de ordenação para diferentes problemas.

```cpp
#include <iostream>
#include <algorithm>

using namespace std;

int func(int a, int b) {
    return a > b; // vetor ficará em ordem decrescente
} // o padrão é return a < b;

int main() {
    int v[5] = {4, 1, 2, 5, 3};
    sort(v, v + 5, func);
    for (int i = 0; i < 5; i++) {
        cout << v[i] << "\n";
    }
}

```

Em C++ podemos criar uma estrutura chamada `struct`, totalmente personalizável ao nosso problema. _(Após a declaração é necessário ponto e vírgula!)_

- `struct nome { tipo1 nome1; tipo2 nome 2; ... };`

A partir dessa struct, podemos criar novos elementos que possuem as propriedades definidas:

```cpp
#include <iostream>
#include <algorithm>

using namespace std;

struct aluno { // criando um tipo aluno
    string nome;
    double media;
};

int main() {
    aluno a, b; // criando um aluno 'a' e um aluno 'b'
    a.nome = "Gustavo"; // atribuindo valores
    b.nome = "Lucas";

    cin >> a.media >> b.media; // atribuindo valores

    cout << a.nome << " " << a.media << "\n";
    cout << b.nome << " " << b.media << "\n";
    return 0;
}
```

É possível criar um vetor de um tipo criado com `struct` e ordená-lo por meio da função `sort()`. Ademais, podemos definir uma _função personalizada_ e passá-la como parâmetro para `sort()`.

```cpp
#include <iostream>
#include <algorithm>

using namespace std;

struct Aluno { // criando o tipo aluno
  string nome;
  double nota;  
}; // PONTO E VÍRGULA !! =)

bool comparaAlunos(Aluno a, Aluno b) {
  return a.nota < b.nota; // prioridade para as menores notas (ordem crescente)
}

int main() {
  Aluno aluno[3]; // criando um vetor de alunos

  for (int i = 0; i < 3; i++) {
    cin >> aluno[i].nome >> aluno[i].nota; // lendo o nome e a nota de cada aluno
  }

  sort(aluno, aluno + 3, comparaAlunos); // ordenando

  for (int i = 0; i < 3; i++) {
    cout << aluno[i].nome << " " << aluno[i].nota << "\n"; // imprimindo cada aluno
}
```