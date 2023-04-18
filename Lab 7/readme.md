# SE_Lab7_202001450

IT-314 Assignment 7


Name: Thakrar Parth N.

Student ID: 202001450

## Section A

### Equivalence class test cases

#### Valid input dates:

(1, 1, 1900) through (31, 12, 2015)

#### Invalid input dates:

(0, 1, 1900) through (31, 0, 1900)

(32, 1, 1900) through (31, 13, 1900)

(1, 1, 1899) through (31, 12, 1899)

(1, 1, 2016) through (31, 12, 9999)

### Equivalence Partitioning

| Tester Action and Input Data | Expected Outcome |
| ---- | --- |
| Valid input: day=1, month=1, year=1900 | Invalid Date |
| Valid input: day=15, month=6, year=2000 | Previous Date |
| Invalid input: day=31, month=4, year=2010 | Invalid Date |
| Invalid input: day=29, month=2, year=2003 | Invalid Date |
| Invalid input: day=0, month=6, year=2000 | Invalid Date |

### Boundary Value Analysis

| Tester Action and Input Data | Expected Outcome |
| ---- | --- |
| Valid input: day=1, month=1, year=1900 | Invalid Date |
| Valid input: day=31, month=12, year=2015 | Previous Date |
| Valid input: day=2, month=1, year=1900 | Previous Date |
| Valid input: day=30, month=12, year=2015 | Previous Date |
| Invalid input: day=0, month=1, year=1900 | Invalid Date |
| Invalid input: day=32, month=12, year=2015 | Invalid Date |

## Problem 1

```java
import org.junit.Test;
import static org.junit.Assert.*;

public class LinearSearchTest {

  @Test
  public void testExistingValue() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(3, arr);
    assertEquals(2, index);
  }

  @Test
  public void testNonExistingValue() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(6, arr);
    assertEquals(-1, index);
  }

  @Test
  public void testFirstElement() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(1, arr);
    assertEquals(0, index);
  }

  @Test
  public void testLastElement() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(5, arr);
    assertEquals(4, index);
  }

  @Test
  public void testEmptyArray() {
    int[] arr = {};
    int index = linearSearch(1, arr);
    assertEquals(-1, index);
  }

  @Test
  public void testNullArray() {
    int[] arr = null;
    int index = linearSearch(1, arr);
    assertEquals(-1, index);
  }
}
```

### Equivalence Partitioning

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Array a[] contains the single occurrence of value v</td>
      <td>The index of v</td>
    </tr>
    <tr>
      <td>Array a[] contains the multiple occurrences of value v</td>
      <td>The first index of value v</td>
    </tr>
    <tr>
      <td>Array a[] does not contain the value v</td>
      <td>-1</td>
    </tr>
  </tbody>
</table>

### Boundary Value Analysis:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Array a[] is empty</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>Array a[] of length 1 and v does not exist in array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>Array a[] of length 1 and v exists in array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Array a[] of length greater than 1 and v does not exist in array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>Array a[] of length greater than 1 and v exists in the beginning of array</td>
      <td>0</td>
    </tr>
     <tr>
      <td>Array a[] of length greater than 1 and v exists in the end of array</td>
      <td>Last index of array</td>
    </tr>
  </tbody>
</table>
</br>

## Problem 2 

### Equivalence Partitioning

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Array a[] contains the single occurrence of value v</td>
      <td>1</td>
    </tr>
    <tr>
      <td>Array a[] contains the multiple occurrences of value v</td>
      <td>The number of occurrence of value v</td>
    </tr>
    <tr>
      <td>Array a[] does not contain the value v</td>
      <td>0</td>
    </tr>
  </tbody>
</table>

### Boundary Value Analysis:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Array a[] is empty</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Array a[] of length 1 and v does not exist in array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Array a[] of length 1 and v exists in array</td>
      <td>1</td>
    </tr>
    <tr>
      <td>Array a[] of length greater than 1 and v does not exist in array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Array a[] of length greater than 1 and v exists in the beginning of array</td>
      <td>The number of occurrence of value v</td>
    </tr>
     <tr>
      <td>Array a[] of length greater than 1 and v exists in the end of array</td>
      <td>The number of occurrence of value v</td>
    </tr>
  </tbody>
</table>
</br>

## Problem 3

### Equivalence Partitioning:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>v=5, a=[1, 3, 5, 7, 9]</td>
    <td>2</td>
  </tr>
  <tr>
    <td>v=1, a=[1, 3, 5, 7, 9]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=9, a=[1, 3, 5, 7, 9]</td>
    <td>4</td>
  </tr>
  <tr>
    <td>v=4, a=[1, 3, 5, 7, 9]</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>v=11, a=[1, 3, 5, 7, 9]</td>
    <td>-1</td>
  </tr>
</table>

### Boundary Value Analysis:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>v=1, a=[1]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=9, a=[9]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=5, a=[]</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>v=5, a=[5, 7, 9]</td>
    <td>0 (smallest element in the array)</td>
  </tr>
  <tr>
    <td>v=5, a=[1, 3, 5]</td>
    <td>2 (largest element in the array)</td>
  </tr>
</table>
</br>

## Problem 4

### Equivalence Partitioning:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: a=3, b=3, c=3</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=4, b=4, c=5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=5, b=4, c=3</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=0, c=0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=-1, b=2, c=3</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Valid input: a=1, b=1, c=1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=2, b=2, c=1</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=3, b=4, c=5</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=1, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=0, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=1, c=0</td>
    <td>INVALID</td>
  </tr>
</table>

### Boundary Value Analysis:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Invalid inputs: a = 0, b = 0, c = 0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid inputs: a + b = c or b + c = a or c + a = b (a=3, b=4, c=8)</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 100</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = b ≠ c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a ≠ b = c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = c ≠ b = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Scalene triangles: a = b + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: b = a + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: c = a + b - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Maximum values: a, b, c = Integer.MAX_VALUE</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Minimum values: a, b, c = Integer.MIN_VALUE</td>
    <td>INVALID</td>
  </tr>
</table>
</br>

## Problem 5

### Equivalence Partitioning:
<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "hello", s2 = "hello world"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "a", s2 = "abc"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "", s2 = "hello world"</td>
    <td>false</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "world", s2 = "hello world"</td>
    <td>false</td>
  </tr>
</table>

### Boundary Value Analysis:
<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>s1 = "", s2 = "abc"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "ab", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "ab"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "ab"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "aaaaaaaaaaaaaaaaaaaaaa", s2 = "aaaaaaaaaaaaaaaaaaaaaab"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "a"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = " "</td>
    <td>False</td>
  </tr>
</table>
</br>

## Problem 6

### (a) Equivalence Classes:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>a = -1, b = 2, c = 3</td>
    <td>Invalid input</td>
  </tr>
  <tr>
    <td>a = 1, b = 1, c = 1</td>
    <td>Equilateral triangle</td>
  </tr>
  <tr>
    <td>a = 2, b = 2, c = 3</td>
    <td>Isosceles triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 4, c = 5</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 5, c = 4</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 5, b = 3, c = 4</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 4, c = 6</td>
    <td>Not a triangle</td>
  </tr>
</table>


### b) Test cases:

Invalid inputs: a = 0, b = 0, c = 0, a + b = c, b + c = a, c + a = b

Invalid inputs: a = -1, b = 1, c = 1, a + b = c

Equilateral triangles: a = b = c = 1, a = b = c = 100

Isosceles triangles: a = b = 10, c = 5; a = c = 10, b = 3; b = c = 10, a = 6

Scalene triangles: a = 4, b = 5, c = 6; a = 10, b = 11, c = 13

Right angled triangle: a = 3, b = 4, c = 5; a = 5, b = 12, c = 13

Non-triangle: a = 1, b = 2, c = 3

Non-positive input: a = -1, b = -2, c = -3


### c) Boundary condition A + B > C:

a = Integer.MAX_VALUE, b = Integer.MAX_VALUE, c = 1

a = Double.MAX_VALUE, b = Double.MAX_VALUE, c = Double.MAX_VALUE


### d) Boundary condition A = C:

a = Integer.MAX_VALUE, b = 2, c = Integer.MAX_VALUE

a = Double.MAX_VALUE, b = 2.5, c = Double.MAX_VALUE


### e) Boundary condition A = B = C:

a = Integer.MAX_VALUE, b = Integer.MAX_VALUE, c = Integer.MAX_VALUE

a = Double.MAX_VALUE, b = Double.MAX_VALUE, c = Double.MAX_VALUE


### f) Boundary condition A^2 + B^2 = C^2:

a = Integer.MAX_VALUE, b = Integer.MAX_VALUE, c = Integer.MAX_VALUE

a = Double.MAX_VALUE, b = Double.MAX_VALUE, c = Math.sqrt(Math.pow(Double.MAX_VALUE, 2) + Math.pow(Double.MAX_VALUE, 2))


### g) Non-triangle:

a = 1, b = 2, c = 4

a = 2, b = 4, c = 8


### h) Non-positive input:

a = -1, b = -2, c = -3

a = 0, b = 1, c = 2


## Section B

### 1. Control Flow Graph (CFG):
```
        +-----+
        | i = 1|
        +-----+
           |
           |
           v
+---------------+
| i < p.size()   |
+---------------+
     | true
     |
     v
+-----------------------+
| ((Point)p.get(i)).y < ((Point)p.get(min)).y |
+-----------------------+
    | true        | false
    |             |
    v             v
+---------------+    +---------------+
| min = i       |    | i++           |
+---------------+    +---------------+
     |                   |
     |                   |
     v                   v
+---------------+    +---------------+
| i < p.size()   |    | return doStack(p) |
+---------------+    +---------------+
     | false             |
     |                   |
     v                   v
+------------------------+
| ((Point)p.get(i)).y == ((Point)p.get(min)).y |
+------------------------+
        | true           | false
        |                |
        v                v
+------------------------+  +---------------+
| ((Point)p.get(i)).x > ((Point)p.get(min)).x|
+------------------------+  +---------------+
        | true           | false
        |                |
        v                v
+---------------+    +---------------+
| min = i       |    | i++           |
+---------------+    +---------------+
        |                |
        |                |
        v                v
+---------------+    +---------------+
| i < p.size()   |    | return doStack(p) |
+---------------+    +---------------+
        | false            |
        |                  |
        v                  v
+--------------------------+
| return doStack(p)         |
+--------------------------+
```


### 2. Test sets for each coverage criterion:

#### a. Statement Coverage:
- Test 1: p = {new Point(0, 0), new Point(1, 1)}
- Test 2: p = {new Point(0, 0), new Point(1, 0), new Point(2, 0)}

#### b. Branch Coverage:
- Test 1: p = {new Point(0, 0), new Point(1, 1)}
- Test 2: p = {new Point(0, 0), new Point(1, 0), new Point(2, 0)}
- Test 3: p = {new Point(0, 0), new Point(1, 0), new Point(1, 1)}

#### c. Basic Condition Coverage:
- Test 1: p = {new Point(0, 0), new Point(1, 1)}
- Test 2: p = {new Point(0, 0), new Point(1, 0), new Point(2, 0)}
- Test 3: p = {new Point(0, 0), new Point(1, 0), new Point(1, 1)}
- Test 4: p = {new Point(0, 0), new Point(1, 0), new Point(0, 1)}
- Test 5: p = {new Point(0, 0), new Point(0, 1), new Point(1, 1)}
