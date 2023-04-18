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

| Input Date | Expected Outcome |
| ---- | --- |
| Valid input: day=1, month=1, year=1900 | Invalid Date |
| Valid input: day=15, month=6, year=2000 | Previous Date |
| Invalid input: day=31, month=4, year=2010 | Invalid Date |
| Invalid input: day=29, month=2, year=2003 | Invalid Date |
| Invalid input: day=0, month=6, year=2000 | Invalid Date |

### Boundary Value Analysis

| Input Date | Expected Outcome |
| ---- | --- |
| Valid input: day=1, month=1, year=1900 | Invalid Date |
| Valid input: day=31, month=12, year=2015 | Previous Date |
| Valid input: day=2, month=1, year=1900 | Previous Date |
| Valid input: day=30, month=12, year=2015 | Previous Date |
| Invalid input: day=0, month=1, year=1900 | Invalid Date |
| Invalid input: day=32, month=12, year=2015 | Invalid Date |
