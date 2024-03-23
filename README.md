#include <iostream>
#include <string>
class Train {
private:
    int trainNumber;
    std::string startStation;
    std::string endStation;
    double price;
public:
    Train(int number, const std::string& start, const std::string& end, double cost)
        : trainNumber(number), startStation(start), endStation(end), price(cost) {}
    int getTrainNumber() const { return trainNumber; }
    std::string getStartStation() const { return startStation; }
    std::string getEndStation() const { return endStation; }
    double getPrice() const { return price; }
};
int main() {
    // Створення об'єкта потягу
    Train train1(101, "Київ", "Львів", 250.0);
    // Виведення інформації про потяг
    std::cout << "Потяг #" << train1.getTrainNumber() << " з " << train1.getStartStation()
              << " до " << train1.getEndStation() << ". Ціна: " << train1.getPrice() << " грн.\n";
    return 0;
}
