# NumPy


What is NumPy?
NumPy (Numerical Python) is a Python library used for fast numerical calculations, array manipulation, mathematical operations, and scientific computing.

NumPy is widely used in:
- Machine Learning and Artificial Intelligence
- Data analysis with Pandas
- Deep Learning with TensorFlow
- Financial calculations and statistical analysis
- Scientific computing
Install NumPy:
python -m pip install numpy


Import the library:
import numpy as np



Here, np is the conventional alias for NumPy.
2. Why do we use NumPy?
Python lists are flexible, but NumPy arrays are designed for efficient numerical computation.
import numpy as np# Python listnumbers = [10, 20, 30]# NumPy arrayarr = np.array([10, 20, 30])print(arr * 2)



Output:
[20 40 60]


Multiplying a normal Python list by 2 repeats the list, whereas multiplying a NumPy array by 2 multiplies each element.
3. NumPy Array (ndarray)
An array is a collection of elements stored in a structured form.
One-dimensional array (1D)
import numpy as nparr = np.array([10, 20, 30, 40])print(arr)print(arr.ndim)print(arr.shape)print(arr.size)



Output:
[10 20 30 40]
1
(4,)
4


- ndim: Number of dimensions.
- shape: Size along each dimension.
- size: Total number of elements.
Two-dimensional array (2D)
import numpy as nparr = np.array([    [10, 20, 30],    [40, 50, 60]])print(arr)print("Dimensions:", arr.ndim)print("Shape:", arr.shape)print("Size:", arr.size)



Output:
[[10 20 30]
 [40 50 60]]
Dimensions: 2
Shape: (2, 3)
Size: 6


The shape (2, 3) means 2 rows and 3 columns.
Array dimensions at a glance
1D

[10, 20, 30]

Vector


2D

[[1, 2], [3, 4]]

Matrix


3D

Multiple matrices

Tensor-like data



NumPy supports arrays of one or more dimensions. TensorFlow uses its own Tensor type.

4. Creating NumPy arrays
np.array()
Creates an array from a Python list or another sequence.
import numpy as npnumbers = np.array([100, 200, 300])print(numbers)



np.zeros()
Creates an array filled with zeros.
arr = np.zeros(5)print(arr)



Output:
[0. 0. 0. 0. 0.]


np.ones()
Creates an array filled with ones.
arr = np.ones((2, 3))print(arr)



Output:
[[1. 1. 1.]
 [1. 1. 1.]]


np.arange()
Creates evenly spaced values using a step size.
arr = np.arange(1, 10, 2)print(arr)



Output:
[1 3 5 7 9]


The stop value 10 is excluded.
np.linspace()
Creates a specified number of evenly spaced values between two endpoints.
arr = np.linspace(0, 10, 5)print(arr)



Output:
[ 0.   2.5  5.   7.5 10. ]


Unlike arange(), linspace() includes the endpoint by default.
5. Array indexing and slicing
Indexing accesses an individual element. Python and NumPy use zero-based indexing.
import numpy as nparr = np.array([10, 20, 30, 40, 50])print(arr[0])print(arr[2])print(arr[-1])



Output:
10
30
50


Slicing
print(arr[1:4])



Output:
[20 30 40]


The starting index is included, but the ending index is excluded.
Accessing 2D elements
matrix = np.array([    [10, 20, 30],    [40, 50, 60]])print(matrix[0, 1])print(matrix[1, 2])



Output:
20
60


matrix[0, 1] means row 0, column 1.
6. Mathematical operations
NumPy performs operations element by element when arrays have compatible shapes.
import numpy as npa = np.array([10, 20, 30])b = np.array([1, 2, 3])print(a + b)print(a - b)print(a * b)print(a / b)



Output:
[11 22 33]
[ 9 18 27]
[10 40 90]
[10. 10. 10.]


Important mathematical functions
Function	Purpose
np.sum(arr)	Calculate total
np.mean(arr)	Calculate average
np.median(arr)	Find median
np.min(arr)	Find minimum
np.max(arr)	Find maximum
np.std(arr)	Calculate standard deviation
np.sqrt(arr)	Calculate square roots
np.round(arr, 2)	Round values to 2 decimal places

Example:
import numpy as npsalaries = np.array([25000, 30000, 45000, 50000])print("Total:", np.sum(salaries))print("Average:", np.mean(salaries))print("Minimum:", np.min(salaries))print("Maximum:", np.max(salaries))



Output:
Total: 150000
Average: 37500.0
Minimum: 25000
Maximum: 50000


7. Reshaping arrays
reshape() changes an array's dimensions without changing the number of elements.
import numpy as nparr = np.arange(1, 7)matrix = arr.reshape(2, 3)print(matrix)



Output:
[[1 2 3]
 [4 5 6]]


Six elements can be reshaped into 2 rows and 3 columns because \(2 \times 3 = 6\).

To flatten an array:
print(matrix.flatten())



Output:
[1 2 3 4 5 6]


8. Filtering arrays with conditions
Boolean filtering selects elements that satisfy a condition.
import numpy as npexpenses = np.array([2500, 7000, 12000, 45000, 3000])high_expenses = expenses[expenses > 10000]print(high_expenses)



Output:
[12000 45000]


You can also combine conditions:
print(expenses[(expenses >= 3000) & (expenses <= 12000)])



Output:
[ 7000 12000  3000]


Use & for element-wise AND and | for element-wise OR. Put each comparison in parentheses.
9. Aggregation with axis
The axis argument specifies the direction in which an operation is performed.
import numpy as nparr = np.array([    [10, 20, 30],    [40, 50, 60]])print("Total:", np.sum(arr))print("Column totals:", np.sum(arr, axis=0))print("Row totals:", np.sum(arr, axis=1))



Output:
Total: 210
Column totals: [50 70 90]
Row totals: [ 60 150]


- axis=0: Operates down the rows, returning one result per column.
- axis=1: Operates across the columns, returning one result per row.
This is especially useful for analyzing financial reports across accounts or months.
10. Sorting and unique values
import numpy as npamounts = np.array([5000, 2000, 5000, 8000, 2000])print(np.sort(amounts))print(np.unique(amounts))



Output:
[2000 2000 5000 5000 8000]
[2000 5000 8000]


- np.sort() returns sorted values.
- np.unique() returns distinct values.
11. Joining and splitting arrays
Joining
a = np.array([1, 2])b = np.array([3, 4])print(np.concatenate((a, b)))



Output:
[1 2 3 4]


Splitting
arr = np.array([10, 20, 30, 40, 50, 60])print(np.split(arr, 3))



Output:
[array([10, 20]), array([30, 40]), array([50, 60])]


np.split() requires equal division sizes when splitting into a specified number of sections.
12. Broadcasting
Broadcasting allows NumPy to perform operations between compatible arrays of different shapes.
import numpy as npsalaries = np.array([25000, 30000, 35000])updated_salaries = salaries + 2000print(updated_salaries)



Output:
[27000 32000 37000]


NumPy automatically adds 2000 to each element. This avoids writing a manual loop.
13. NumPy in your Company Account project
Suppose you want to analyze company expenses. NumPy can calculate totals, averages, and expense thresholds.
import numpy as npexpenses = np.array([15000, 2500, 3200, 12000, 45000])print("Total expenses:", np.sum(expenses))print("Average expense:", np.mean(expenses))print("Largest expense:", np.max(expenses))# Flag expenses above a review thresholdflagged = expenses[expenses > 10000]print("Expenses for review:", flagged)



Output:
Total expenses: 77700
Average expense: 15540.0
Largest expense: 45000
Expenses for review: [15000 12000 45000]


These flags identify transactions for further review; they do not prove fraud or errors. For real accounting software, use a proper double-entry ledger, decimal-safe monetary calculations, and database transactions. NumPy is useful for analysis, but binary floating-point arrays should not be the authoritative storage for currency amounts.
14. How NumPy connects with Pandas and TensorFlow
Pandas

Load, clean, and organize financial data

NumPy

Perform numerical calculations and prepare arrays

TensorFlow

Train a model for expense forecasting or anomaly detection


Example of converting NumPy data into a TensorFlow tensor:
import numpy as npimport tensorflow as tfexpenses = np.array([15000, 2500, 3200], dtype=np.float32)tensor = tf.convert_to_tensor(expenses)print(tensor)



NumPy and TensorFlow are separate libraries: NumPy uses ndarray, while TensorFlow uses Tensor.
