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
      <td>The number od occurrence of value v</td>
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
      <td>The number od occurrence of value v</td>
    </tr>
     <tr>
      <td>Array a[] of length greater than 1 and v exists in the end of array</td>
      <td>The number od occurrence of value v</td>
    </tr>
  </tbody>
</table>
</br>
