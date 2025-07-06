# Simple C++ Machine Learning Example

This repository contains a basic linear regression demo implemented in C++.  
It calculates the best-fit line `y = mx + b` using hardcoded sample data and predicts new values.

##  Technologies Used
- C++  
- Basic math (no external libraries)  


#include <iostream>
using namespace std;

// Simple Linear Regression y = mx + b
int main() {
    double x[] = {1, 2, 3, 4, 5};
    double y[] = {2, 4, 6, 8, 10}; // y = 2x (perfect linear relationship)
    int n = 5;

    double sumX = 0, sumY = 0, sumXY = 0, sumXX = 0;
    for(int i = 0; i < n; i++) {
        sumX += x[i];
        sumY += y[i];
        sumXY += x[i] * y[i];
        sumXX += x[i] * x[i];
    }

    double m = (n * sumXY - sumX * sumY) / (n * sumXX - sumX * sumX);
    double b = (sumY - m * sumX) / n;

    cout << "Model: y = " << m << "x + " << b << endl;

    // Predict new value
    double newX = 6;
    double predY = m * newX + b;
    cout << "Prediction for x = " << newX << ": y = " << predY << endl;

    return 0;
}
