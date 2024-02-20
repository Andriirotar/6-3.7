#include <iostream>
#include <cmath>
// Базовий клас "Геометрична фігура"
class Shape {
public:
    virtual void display() const = 0; // Чисто віртуальна функція для виведення інформації про фігуру
    virtual ~Shape() {} // Віртуальний деструктор
};
// Похідний клас "Коло"
class Circle : public Shape {
protected:
    double radius;
public:
    Circle(double _radius) : radius(_radius) {}
    void display() const override {
        std::cout << "Circle with radius: " << radius << std::endl;
    }
};
// Похідний клас "Квадрат"
class Square : public Shape {
protected:
    double side;
public:
    Square(double _side) : side(_side) {}
    void display() const override {
        std::cout << "Квадрат зі стороною: " << side << std::endl;
    }
};
// Похідний клас "Вписане коло в квадрат"
class InscribedCircle : public Circle, public Square {
public:
    InscribedCircle(double _side) : Circle(_side / sqrt(2)), Square(_side) {}
    void display() const override {
        std::cout << "Вписане коло з радіусом: " << radius << " in square with side: " << side << std::endl;
    }
};
int main() {
    // Створення об'єктів класів
    Circle circle(5.0);
    Square square(10.0);
    InscribedCircle inscribedCircle(10.0);
    // Виведення інформації про об'єкти
    std::cout << "Information about shapes:" << std::endl;
    circle.display();
    square.display();
    inscribedCircle.display();
    return 0;
}
