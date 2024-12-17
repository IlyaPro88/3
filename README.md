// Интерфейс с методом go()
interface Movable {
    void go();
}

// Класс Car, реализующий интерфейс Movable
class Car implements Movable {
    private String brand;
    private String model;
    private int year;

    // Конструктор для всех полей
    public Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // Реализация метода go() из интерфейса
    @id86240433 (@Override)
    public void go() {
        System.out.println("Машина " + brand + " " + model + " поехала!");
    }

    // Геттеры
    public String getBrand() {
        return brand;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }

    // Сеттеры
    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setYear(int year) {
        this.year = year;
    }
}

// Абстрактный класс Human
abstract class Human {
    protected String name;

    public Human(String name) {
        this.name = name;
    }

    // Абстрактный метод
    public abstract void displayInfo();
}

// Класс Women, наследующий Human
class Women extends Human {
    private int age;

    public Women(String name, int age) {
        super(name);
        this.age = age;
    }

    // Метод для ввода возраста
    public void setAge(int age) {
        this.age = age;
    }

    // Метод для вывода возраста
    public int getAge() {
        return age;
    }

    // Переопределение метода displayInfo
    @id86240433 (@Override)
    public void displayInfo() {
        System.out.println("Женщина: " + name + ", Возраст: " + age);
    }
}

// Класс Men, наследующий Human
class Men extends Human {
    private String profession;

    public Men(String name, String profession) {
        super(name);
        this.profession = profession;
    }

    // Переопределение метода displayInfo
    @id86240433 (@Override)
    public void displayInfo() {
        System.out.println("Мужчина: " + name + ", Профессия: " + profession);
    }
}

// Главный класс для запуска программы
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // Работа с интерфейсом и классом Car
        Car car = new Car("Toyota", "Camry", 2020);
        car.go();

        System.out.println("Марка машины: " + car.getBrand());
        System.out.println("Модель машины: " + car.getModel());
        System.out.println("Год выпуска: " + car.getYear());

        System.out.println();

        // Работа с абстрактным классом и его наследниками
        Scanner scanner = new Scanner(System.in);

        System.out.print("Введите имя женщины: ");
        String name = scanner.nextLine();

        System.out.print("Введите возраст женщины: ");
        int age = scanner.nextInt();

        Women woman = new Women(name, age);
        woman.displayInfo();

        System.out.println();

        Men man = new Men("Иван", "Инженер");
        man.displayInfo();
    }
}
