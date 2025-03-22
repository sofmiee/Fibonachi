import java.math.BigInteger; //импортируем класс BigInteger для очень больших чисел
import java.util.Scanner;

public class Fibonachi {
    public static boolean square(BigInteger x) { //проверяем число на квадратность
        BigInteger s = x.sqrt();
        return s.multiply(s).equals(x); //так как числа типа BigInteger не усваивают операторы +,-,*,/, умножаем методом multiply()
    }

    public static boolean check(BigInteger n) { //проверяем на принадлежность фибоначчи с помощью 5n^2+4 и 5n^-4
        // Проверяем два условия
        if (n.compareTo(BigInteger.ONE) <= 0) { //BigInteger.ONE это 1, compareTo сравнивает числа n<1 -> -1, n=1 -> 0
            throw new IllegalArgumentException("Число должно быть натуральным и больше 1."); //выкидываем ошибку
        }else{
            return square(n.multiply(BigInteger.valueOf(5)).multiply(n).add(BigInteger.valueOf(4))) ||
                    square(n.multiply(BigInteger.valueOf(5)).multiply(n).subtract(BigInteger.valueOf(4)));
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in); //открываем считыватель
        System.out.println("Введите число: ");
        if (sc.hasNextBigInteger()) { //проверяем, ввели ли что-то
            BigInteger number = sc.nextBigInteger();
            if (check(number)) {
                System.out.printf("Число %s лежит в последовательности Фибоначчи.%n", number); //%n переносит на новую строку
            } else {
                System.out.printf("Число %s не лежит в последовательности Фибоначчи.%n", number);
            }

        }
        sc.close();
    }
}
