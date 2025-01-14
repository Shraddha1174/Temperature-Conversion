#include <iostream>
#include <iomanip>
#include <cctype> // For toupper()

using namespace std;

// Function to convert Celsius to Fahrenheit and Kelvin
void convertFromCelsius(double temp) {
    double fahrenheit = (temp * 9.0 / 5.0) + 32.0;
    double kelvin = temp + 273.15;

    cout << fixed << setprecision(2);
    cout << "Temperature in Fahrenheit: " << fahrenheit << " °F" << endl;
    cout << "Temperature in Kelvin: " << kelvin << " K" << endl;
}

// Function to convert Fahrenheit to Celsius and Kelvin
void convertFromFahrenheit(double temp) {
    double celsius = (temp - 32.0) * 5.0 / 9.0;
    double kelvin = celsius + 273.15;

    cout << fixed << setprecision(2);
    cout << "Temperature in Celsius: " << celsius << " °C" << endl;
    cout << "Temperature in Kelvin: " << kelvin << " K" << endl;
}

// Function to convert Kelvin to Celsius and Fahrenheit
void convertFromKelvin(double temp) {
    double celsius = temp - 273.15;
    double fahrenheit = (celsius * 9.0 / 5.0) + 32.0;

    cout << fixed << setprecision(2);
    cout << "Temperature in Celsius: " << celsius << " °C" << endl;
    cout << "Temperature in Fahrenheit: " << fahrenheit << " °F" << endl;
}

int main() {
    double temperature;
    char unit;

    cout << "Enter the temperature value: ";
    cin >> temperature;
    cout << "Enter the unit of temperature (C for Celsius, F for Fahrenheit, K for Kelvin): ";
    cin >> unit;

    // Convert to uppercase for case-insensitivity
    unit = toupper(unit);

    // Convert based on the input unit
    switch (unit) {
        case 'C':
            cout << "Converting from Celsius..." << endl;
            convertFromCelsius(temperature);
            break;
        case 'F':
            cout << "Converting from Fahrenheit..." << endl;
            convertFromFahrenheit(temperature);
            break;
        case 'K':
            cout << "Converting from Kelvin..." << endl;
            convertFromKelvin(temperature);
            break;
        default:
            cout << "Invalid unit entered. Please enter C, F, or K." << endl;
    }

    return 0;
}