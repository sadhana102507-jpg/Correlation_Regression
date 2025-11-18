# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```
Name:SADHANA R
Register No:25017643
Slot Name:3P1-1
```
```
import numpy as np
import math
import matplotlib.pyplot as plt
# Input x and y values (space separated), e.g.:
# x: 1 2 3 4 5
# y: 2 4 3 5 7
x = [int(i) for i in input("Enter x values (space separated): ").split()]
y = [int(i) for i in input("Enter y values (space separated): ").split()]
if len(x) != len(y):
  raise SystemExit("Error: x and y must have the same number of values.")
N = len(x)
Sx = 0
Sy = 0
Sxy = 0
Sx2 = 0
Sy2 = 0
for i in range(N):
  Sx += x[i]
  Sy+= y[i]
  Sxy += x[i] * y[i]
  Sx2 += x[i]**2
  Sy2 += y[i]**2
# Correlation coefficient r
den = math.sqrt((N * Sx2 - Sx**2) * (N * Sy2 - Sy**2))
if den == 0:
  raise SystemExit("Denominator zero when computing correlation.")
r = (N * Sxy - Sx * Sy) / den
print("The Correlation coefficient is %0.3f" % r)
# Regression coefficient (slope) of Y on X
byx = (N * Sxy - Sx * Sy) / (N * Sx2 - Sx**2)
# Means
xmean = Sx / N
ymean = Sy / N
print("The Regression line Y on X is ::: y = %0.3f + %0.3f (x-%0.3f)" % (ymean, byx, 
xmean))
# Scatter plot of data points
plt.scatter(x, y)
# Regression function and plot
def Reg(xv):
  return ymean + byx * (xv - xmean)
x_plot = np.linspace(min(x), max(x), 51)
y_plot = Reg(x_plot)
plt.plot(x_plot, y_plot, 'r')
plt.xlabel('x-data')
plt.ylabel('y-data')
plt.legend(['Regression Line', 'Data points'])
plt.grid(True)
plt.show()
```
https://colab.research.google.com/drive/1E2Qlb3rZgWSM9Rz1n4mhxEsasEEdWTsO?usp=sharing
# Output 
```
Enter x values (space separated): 25 28 35 32 31 36 29 38 34 32
Enter y values (space separated): 43 46 49 41 36 32 3 30 33 39
The Correlation coefficient is -0.020
The Regression line Y on X is ::: y = 35.200 + -0.064 (x-32.000)
```
<img width="693" height="529" alt="Screenshot 2025-11-18 134842" src="https://github.com/user-attachments/assets/8069539b-79c1-4121-9a10-60d99e23aa68" />

# Result
The correlation and regression for data analysis of objects from feeder using probability distribution are calculated.
