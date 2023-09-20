#include <iostream>
#include <climits>
int main()
{
    int n;    // Розмір масиву
    int c, d; // Діапазон [c, d]
    std::cout << "Введіть розмір масиву: ";
    std::cin >> n;
    int arr[n];
    std::cout << "Введіть елементи масиву: ";
    for (int i = 0; i < n; i++)
    {
        std::cin >> arr[i];
    }
    std::cout << "Введіть діапазон [c, d]: ";
    std::cin >> c >> d;
    int maxElement = INT_MIN; // Початкове значення максимального елемента
    int maxIndex = -1;        // Початкове значення позиції максимального елемента
    for (int i = 0; i < n; i++)
    {
        if (arr[i] >= c && arr[i] <= d)
        {
            if (arr[i] % 2 == 0)
            {
                break; // Зупиняємося, якщо знайдено парний елемент
            }
            if (arr[i] >= maxElement)
            {
                maxElement = arr[i];
                maxIndex = i;
            }
        }
    }
    if (maxIndex != -1)
    {
        std::cout << "Номер останнього максимального елемента: " << maxIndex << std::endl;
    }
    else
    {
        std::cout << "Максимальний елемент не знайдено в заданому діапазоні та до першого парного елемента." << std::endl;
    }
    return 0;
}
