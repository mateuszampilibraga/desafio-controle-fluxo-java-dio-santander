
# DesafioControleFluxo

## Descrição do Projeto
Este projeto é a solução para o desafio proposto no módulo de Controle de Fluxo da trilha Java Básico da Digital Innovation One (DIO).

## Objetivo do Desafio
O objetivo deste desafio é exercitar os conceitos de controle de fluxo em Java, codificando um cenário onde o sistema deve receber dois parâmetros via terminal que representarão dois números inteiros. A partir desses números, o sistema deve calcular a quantidade de interações (loops) e imprimir no console os números incrementados. Se o primeiro parâmetro for maior que o segundo, o sistema deve lançar uma exceção customizada chamada `ParametrosInvalidosException`.

## Cenário
O sistema deve:
1. Receber dois números inteiros via terminal.
2. Verificar se o segundo número é maior que o primeiro. Caso contrário, lançar a exceção `ParametrosInvalidosException` com a mensagem: "O segundo parâmetro deve ser maior que o primeiro".
3. Calcular a quantidade de interações entre os dois números e imprimir no console os números incrementados.

### Exemplo de Uso
Se você passar os números 12 e 30, o sistema realizará 18 interações e imprimirá os números de 1 a 18:
```
Imprimindo o número 1
Imprimindo o número 2
...
Imprimindo o número 18
```

### Exceção Customizada
Se o primeiro parâmetro for maior que o segundo, o sistema lançará a exceção `ParametrosInvalidosException` com a mensagem:
```
"O segundo parâmetro deve ser maior que o primeiro"
```

## Estrutura do Projeto
O projeto consiste em duas classes principais:
1. `Contador.java` - Contém a lógica principal do programa.
2. `ParametrosInvalidosException.java` - Representa a exceção de negócio customizada.

## Implementação

### Contador.java
```java
import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();

        try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException e) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro!");
        }

        terminal.close(); // Fechar o scanner
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroDois <= parametroUm) {
            throw new ParametrosInvalidosException();
        }

        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}
```

### ParametrosInvalidosException.java
```java
public class ParametrosInvalidosException extends Exception {
}
```

## Como Executar
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/mateuszampilibraga/desafio-controle-fluxo-java-dio-santander.git
   ```
2. **Navegue até o diretório do projeto**:
   ```bash
   cd desafio-controle-fluxo-java-dio-santander
   ```
3. **Compile o programa Java**:
   ```bash
   javac Contador.java
   ```
4. **Execute o programa**:
   ```bash
   java Contador
   ```

## Autores
- Mateus Zampili Braga

## Licença
Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](https://github.com/mateuszampilibraga/desafio-controle-fluxo-java-dio-santander/blob/master/LICENSE) para detalhes.

```
