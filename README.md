#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main() {
    vector<int> V = {1, 2, 3, 4, 5, 6}; // Приклад вектора з парною кількістю елементів
    // Пошук першого співпадіння між першою половиною та другою половиною вектора
    auto it = find_first_of(V.begin(), V.begin() + V.size() / 2, V.begin() + V.size() / 2, V.end());
    if (it != V.end()) { // Якщо знайдено співпадіння
        V.insert(it, 0); // Вставка нульового елемента перед знайденим співпадінням
    }
    // Вивід вектора зі змінами
    for (const auto& elem : V) {
        cout << elem << " ";
    }
    cout << endl;
    return 0;
}
