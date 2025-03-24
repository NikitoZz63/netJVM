public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1 Переменная i типа int создаётся в стеке, так как это примитивный тип(Значение 1 хранится прямо в стеке).

        Object o = new Object();        // 2 new создаёт новый объект Object в куче. Переменная o создаётся в стеке и содержит ссылку на этот объект в куче. Объект Object хранится в куче до тех пор, пока есть ссылки на него

        Integer ii = 2;                 // 3 Автоупаковка примитива 2 в объект типа Integer.

        printAll(o, i, ii);             // 4 Вызывается метод printAll, создаётся новый фрейм в стеке
        System.out.println("finished"); // 7 Выводит "finished" в консоль. После завершения метода main стек полностью очищается.
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 Число 700 выходит за диапазон кэширования Integer, поэтому создаётся новый объект в куче. 	Ссылка uselessVar хранится в стеке.

        System.out.println(o.toString() + i + ii);  // 6 o.toString() возвращает строку вида "java.lang.Object@<hashcode>". i (примитив int) и ii (Integer) автоматически конвертируются в строки и конкатенируются.
    }
}

