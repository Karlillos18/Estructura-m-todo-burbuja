# Estructura-m-todo-burbuja
#include <iostream>

// Función para ordenar el arreglo utilizando el método de la burbuja
void bubbleSort(int arr[], int n, bool ascending) {
    for (int i = 0; i < n-1; ++i) {
        for (int j = 0; j < n-i-1; ++j) {
            if (ascending ? arr[j] > arr[j+1] : arr[j] < arr[j+1]) {
                // Intercambio
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}

int main() {
    int arr[10];
    std::cout << "Introduce 10 números enteros separados por espacios: ";
    for (int i = 0; i < 10; ++i) {
        std::cin >> arr[i];
    }

    char order;
    std::cout << "¿En qué orden deseas ordenar los números? (A para ascendente, D para descendente): ";
    std::cin >> order;

    bool ascending = (order == 'A' || order == 'a');

    bubbleSort(arr, 10, ascending);

    std::cout << "Arreglo ordenado: ";
    for (int i = 0; i < 10; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}
