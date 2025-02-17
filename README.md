# Hello, World! ➡️ Functional Programming  

Este repositório contém referências para estudos sobre Programação Funcional.  

## 📚 Referências  

### 📺 Vídeos  
- [Introdução à Programação Funcional | Código Fonte TV](https://www.youtube.com/watch?v=BxbHGPivjdc&ab_channel=C%C3%B3digoFonteTV)  
- [Paradigma Funcional no JavaScript | Attekita Dev](https://www.youtube.com/watch?v=7mVVIayE7A8&ab_channel=AttekitaDev)  
- [Funções Puras e Imutabilidade | Ilustra Dev](https://www.youtube.com/watch?v=8mxqA__vRfY&ab_channel=IlustraDev)  
- [Programação Funcional na Prática | Building Nubank](https://www.youtube.com/watch?v=kVtimAl3VRs&ab_channel=BuildingNubank)  

### 📖 Livros  
- **Estruturas de Dados e Algoritmos com JavaScript** – Loiane Groner  

### 🎓 Cursos  
- [Clojure: Introdução à Programação Funcional | Alura](https://cursos.alura.com.br/course/clojure-introducao-a-programacao-funcional/)

### 💻 Entendendo na prática

#### 1️⃣ POO – Abordagem com Classe e Estado Mutável
```dart
class Contador {
```
🔹 Define uma **classe** chamada `Contador`.  
🔹 Em POO, usamos classes para representar objetos do mundo real.  

```dart
  int valor = 0; // Estado mutável
```
🔹 `valor` é uma variável **mutável** (pode ser alterada).  
🔹 Começa com **0** e será incrementada conforme necessário.  

```dart
  void incrementar() {
    valor++; // Modifica o estado
  }
```
🔹 `incrementar()` é um **método** que aumenta `valor` em 1.  
🔹 Modifica diretamente o **estado interno** da classe, o que pode gerar efeitos colaterais indesejados.  

```dart
void main() {
```
🔹 `main()` é o ponto de entrada do programa.  

```dart
  var contador = Contador();
```
🔹 Criamos um **objeto** da classe `Contador`.  
🔹 Esse objeto armazena o estado (`valor`) dentro dele.  

```dart
  contador.incrementar();
  contador.incrementar();
```
🔹 Chamamos `incrementar()` duas vezes.  
🔹 Cada chamada modifica `valor` dentro do objeto.  

```dart
  print(contador.valor); // Saída: 2
```
🔹 Exibe o valor final do contador, que agora é `2`.  

#### 🤔 Problemas nessa abordagem
- ❌ `valor` é **mutável**, o que pode gerar bugs difíceis de rastrear.  
- ❌ `incrementar()` **muda o estado interno** do objeto, tornando-o menos previsível.  
- ❌ Para testar `incrementar()`, precisamos criar um objeto, o que complica testes.  

#### 2️⃣ FP – Abordagem com Funções Puras e Imutabilidade
```dart
int incrementar(int valor) => valor + 1;
```
🔹 **Função pura**: não altera nada fora dela.  
🔹 Sempre que chamamos `incrementar(3)`, retorna `4` (mesmo input = mesmo output).  
🔹 **Não há estado mutável**, diferente da classe anterior.  

```dart
int aplicar(int x, int Function(int) func) => func(x);
```
🔹 **Função de ordem superior**: recebe outra função como argumento (`func`).  
🔹 Executa `func(x)`, ou seja, aplica a função recebida no valor `x`.  
🔹 Esse conceito permite **reutilização** de código.  

```dart
void main() {
```
🔹 Ponto de entrada do programa.  

```dart
  print(incrementar(0)); // Saída: 1
```
🔹 Chama `incrementar(0)`, que retorna `1`.  
🔹 Como `incrementar()` é **imutável**, `0` **não é alterado**, apenas retorna um novo valor.  

```dart
  print(aplicar(3, incrementar)); // Saída: 4
```
🔹 `aplicar(3, incrementar)` faz o seguinte:  
  - `aplicar()` recebe o número `3` e a função `incrementar`.  
  - Executa `incrementar(3)`, que retorna `4`.  

---

#### ✅ Vantagens dessa abordagem
- **Imutabilidade** → Não altera estado interno, sempre cria um novo valor.  
- **Funções puras** → Sempre retornam o mesmo resultado para os mesmos inputs.  
- **Fácil de testar** → Podemos testar `incrementar(3)` diretamente, sem precisar de objetos.  
- **Modularidade** → `aplicar()` pode ser usado com qualquer outra função que receba um `int`.  

#### 📌 Resumo dos principais pontos
1. Em POO, criamos uma classe `Contador` com um estado mutável (`valor`). O problema? O estado pode mudar em qualquer lugar, tornando o código difícil de prever e testar.
2. Já na Programação Funcional, usamos funções puras e imutáveis. `incrementar(3)` sempre retorna `4`, sem modificar nada. Assim, o código fica mais previsível, modular e fácil de testar.
3. "Além disso, podemos usar funções de ordem superior como `aplicar()`, que recebe uma função e aplica em um valor, tornando o código ainda mais reutilizável.  

## 🚀 Sobre o Repositório  
Se você quer aprender mais sobre Programação Funcional e explorar novas abordagens para escrever código mais conciso e eficiente, confira os materiais acima!  

Caso tenha sugestões de novas referências, fique à vontade para abrir uma issue ou um pull request.  

📩 Conecte-se comigo no [LinkedIn](https://www.linkedin.com/in/leticiacaroline/) ou acesse [meu website](https://www.levxyca.com/).  
