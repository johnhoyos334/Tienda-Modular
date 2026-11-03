#include <iostream>
using namespace std;

double calcularSubtotal(double precio, int cantidad) {
    return precio * cantidad;
}
double calcularDescuento(double subtotal) {
    if (subtotal > 100000) {
        return subtotal * 0.10;
    }
    else {
        return 0;
    }
}
double calcularTotal(double subtotal, double  descuento) {
    return subtotal - descuento;
}
void mostrarResultados(double subtotal, double descuento, double total) {
    cout << "\n--- FACTURA DE COMPRA ---" << endl;
    cout << "Subtotal: $" << subtotal << endl;
    cout << "Descuento: $" << descuento << endl;
    cout << "Total a pagar: $" << total << endl;
}
int main() {
    double precio;
    int cantidad;
    double subtotal;
    double descuento;
    double total;
    cout << "Ingrese el precio unitario: ";
    cin >> precio;
    cout << "Ingrese la cantidad: ";
    cin >> cantidad;
    while (precio < 0 || cantidad < 0) {
        cout << "Error: no se permiten valores negativos." << endl;
        cout << "Ingrese el precio unitario: ";
        cin >> precio;
        cout << "Ingrese la cantidad: ";
        cin >> cantidad;
    }
    subtotal = calcularSubtotal(precio, cantidad);
    descuento = calcularDescuento(subtotal);
    total = calcularTotal(subtotal, descuento);
    mostrarResultados(subtotal, descuento, total);
    return 0;
}
