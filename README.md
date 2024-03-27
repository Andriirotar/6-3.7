#include <iostream>
#include <vector>
#include <algorithm>
struct ClientData {
    int duration;
    int year;
    int month;
    int clientCode;
};
bool compareByYear(const ClientData &a, const ClientData &b) {
    return a.year > b.year;
}
void processClientData(int K, const std::vector<ClientData> &clientData) {
    bool dataFound = false;
    for (int year = 2024; year >= 2000; --year) {
        int maxDuration = 0;
        int maxMonth = -1;
        for (const auto &data : clientData) {
            if (data.clientCode == K && data.year == year && data.duration > maxDuration) {
                maxDuration = data.duration;
                maxMonth = data.month;
                dataFound = true;
            }
        }
        if (dataFound) {
            std::cout << year << " " << maxMonth << " " << maxDuration << std::endl;
            dataFound = false;
        }
    }
    if (!dataFound) {
        std::cout << "Немає даних" << std::endl;
    }
}
int main() {
    std::vector<ClientData> clientData = {
        {3, 2023, 5, 123},
        {2, 2023, 6, 456},
        {4, 2022, 7, 123},
        {5, 2022, 8, 123},
        {6, 2021, 9, 789}
        // Додайте інші дані про клієнтів за потреби
    };
    int K = 123; // код клієнта
    processClientData(K, clientData);
    return 0;
}
