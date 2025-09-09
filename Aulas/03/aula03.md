<h1 style="color:#1BB3FA;">Baseado em TN10, caps 2,3,4.6-4.9</h1>

- Para escopo estático, o ambiente de referência para um nome é o
 seu escopo definidor e todos os sub-escopos aninhados


 ```c
 int h, i;
 void B (int w){
    int j, k;
    i = 2*w; w = w+1;
 }
 void A (int x, int y) {
    float i, j;
    B(h); i = 3;
 }
 void main(){
    int a, b;
    h = 5; a = 3; b = 2;
    A (a,b);
    B (h);
 }

 ```

 - Mais externo: <h,1> <i,1> <B,2> <A,7> <main,11>
 - B: <w,2> <j,3> <k,3>
 - A: <x,7> <y,7> <i,8> <j,8>
 - M: <a,12> <b,12>
  

|Função|Pilha Tabela de Simbolos|
|------|------------------------|
|B     |w,2 j,3 k,3 h,1 i,1 b,2|

- No escopo dinâmico um nome é associado à sua declaração mais recente com base no histórico de execução do programa.
- M -> A -> B - (15)
- M -> B - (17)
- Negativos: Confuso (propenso à erros); Falta de confiabilidade; Mais tempo de processamento;
- Um nome redeclarado em escopo aninhado efetivamente esconde a declaração mais externa.
  - this em java se referencia a variável mais próxima
  - main.x em Ada
- Sobrecarga é quando vc pode utilizar um nome mais de uma vez para ter significados diferentes mas não tão diferentes.
- A sobrecarga usa o número ou tipo de argumento para distinção.
- O tempo de vida de uma variável é o intervalo de tempo o qual a variável tem um bloco de memória alocado para si.