#include <iostream>
#include <vector>
#include <algorithm>
int main() {
    std::vector<int> V = {1, 2, 3, 4, 5, 6}; // Приклад вектора з парною кількістю елементів
    auto middle = V.begin() + V.size() / 2; // Знаходимо середину вектора
    auto it = std::find_first_of(V.begin(), middle, middle, V.end()); // Шукаємо спільний елемент
    if (it != middle) { // Якщо елемент знайдено
        V.insert(it, 0); // Вставляємо нуль перед ним
    }
    // Виводимо вектор
    for (const auto& elem : V) {
        std::cout << elem << " ";
    }
    std::cout << std::endl;
    return 0;
}
