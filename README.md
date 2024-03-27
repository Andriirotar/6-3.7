#include <iostream>
#include <vector>
#include <algorithm>
int main() {
    std::vector<int> V1 = {1, 2, 2, 3, 4, 5};
    std::vector<int> V2 = {2, 3, 3, 4, 5, 6, 6};
    std::sort(V1.begin(), V1.end(), std::greater<int>());
    std::sort(V2.begin(), V2.end(), std::greater<int>());
    std::vector<int> result;
    std::set_symmetric_difference(V1.begin(), V1.end(), V2.begin(), V2.end(), std::back_inserter(result), std::greater<int>());
    for (const auto &num : result) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
    return 0;
}
