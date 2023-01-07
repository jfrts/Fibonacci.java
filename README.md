# Fibonacci.java
Classe simples para calcular sequência de Fibonacci com critérios de paradas.

Uso:
```
int howManyNumbers = 30;
long numberToStop = 1600;

Fibonacci.print(howManyNumbers, numberToStop);
```

A Classe:
```
package org.example;

public class Fibonacci {

    private static long numberToStop;

    private static long calculate(int number) {
        if (number < 2) {
            return number;
        }

        return calculate(number - 1) + calculate(number - 2);
    }

    private static boolean checkStop(long calculatedNumber) {
        return calculatedNumber <= Fibonacci.numberToStop;
    }

    public static void print(int howManyNumbers, long numberToStop) {
        Fibonacci.numberToStop = numberToStop;

        for (int i = 0; i < howManyNumbers; i++) {
            long currentValue = Fibonacci.calculate(i);

            if (checkStop(currentValue)) {
                System.out.print(currentValue + "  ");
            } else {
                break;
            }
        }
    }

}
```
