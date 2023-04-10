# matplotlib.pyplot tutorial

Matplotlib is a powerful 2D plotting library for Python, which allows you to create a wide range of static, animated, and interactive visualizations. To gain a high level of understanding, you should familiarize yourself with the following key concepts, functions, and classes

## Standard alias
```python
import matplotlib.pyplot as plt
```

## Basic components

| Components | Description |
| --- | --- |
|**Figure**|The top-level container for all plot elements, which can include multiple Axes|
|**Axes**| The actual plot, containing the labels, lines, and other visual elements|

## Methods

| Methods | Description |
| --- | --- |
| `plt.plot()` | A simple line plot |
| `plt.scatter()` | A scatter plot |
| `plt.bar()` | A bar plot |
| `plt.hist()` | A histogram |
| `plt.pie()` |  A pie chart |
| `plt.title()` | Add a title to the plot |
| `plt.xlabel(), plt.ylabel()` | Add labels to the x and y axes |
| `plt.xticks(), plt.yticks()` | Customize tick marks and labels on the x and y axes |
| `plt.legend()` | Add a legend to the plot |
| `plt.grid()` | Add gridlines to the plot |
| `plt.xlim(), plt.ylim()` | Set the limits for the x and y axes|
|`plt.subplots()` | Create a grid of subplots within a single Figure|
|`plt.subplot()`| Create a single subplot within a grid|
|`plt.figure()`| Create a new Figure for multiple independent plots|
|`plt.text()`| Add text to the plot at a specific location|
|`plt.annotate()`| Add an annotation with an arrow pointing to a specific point on the plot|
|`plt.savefig()`| Save the current plot as an image file (e.g., PNG, PDF, SVG)|


## Examples

<details><summary><b>Using Figures</b></summary>

```python
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# Create the first figure and plot
plt.figure(1, figsize=(6, 4))
plt.plot(x, y1)
plt.title('Sine Wave')
plt.xlabel('x')
plt.ylabel('sin(x)')

# Create the second figure and plot
plt.figure(2, figsize=(6, 4))
plt.plot(x, y2)
plt.title('Cosine Wave')
plt.xlabel('x')
plt.ylabel('cos(x)')

# Switch back to Figure 1 and add gridlines
plt.figure(1)
plt.grid(True)

# Show both figures
plt.show()
```
    
</details><br>

<details><summary><b>Line Plot</b></summary>
    
```python
x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.plot(x, y, linestyle='--', linewidth=2, color='red', marker='o', markersize=4)
plt.title('Sine Wave')
plt.xlabel('x')
plt.ylabel('sin(x)')
plt.show()

```

</details>

<details><summary>Two Lines Same Plot</summary>

```python
import matplotlib.pyplot as plt
import numpy as np

# Define the demand and supply functions
def demand(price):
    return 10 - price

def supply(price):
    return price - 4

# Create an array of prices
prices = np.linspace(0, 10, 100)

# Calculate the quantity demanded and supplied at each price
quantity_demanded = demand(prices)
quantity_supplied = supply(prices)

# Create a new figure
fig, ax = plt.subplots()

# Plot the demand and supply curves
ax.plot(prices, quantity_demanded, label='Demand')
ax.plot(prices, quantity_supplied, label='Supply')

# Add axes labels and a title
ax.set_xlabel('Price')
ax.set_ylabel('Quantity')
ax.set_title('Supply and Demand Curve')

# Add a legend to the plot
ax.legend()

# Show the plot
plt.show()

```

</details>