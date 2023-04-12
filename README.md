# Lab Report

**Name:** _Vihar Shah_

**ID:** _202001110_

**Lab:** _07_

**Objective:** _Black-box and white-box testing_

---

## Section A

First, I created 5 different JAVA files, namely, P1.jav, P2.java, P3.java, P4.java, and P5.java. Each file contains the corresponding function code to be tested.

> **P1.java** contains code to perform linear search on an array of integers to return the index of a particular integer. If it is not found, _-1_ is returned.

The test cases written for the **_linearSearch(int v, int[] a)_** are as follows

```java
import static org.junit.jupiter.api.Assertions.*;

class P1Test {
	@Test
	void returnIdx1() {
		int[] arr = {-3, 4, -1, 1, 0 ,13 ,5};
		int expected = 3;
		int v = 1;
		assertEquals(P1.linearSearch(v, arr), expected);
	}
	@Test
	void returnIdx2() {
		int[] arr = {-3, 4, -1, -1, 0 ,13 ,5};
		int expected = 2;
		int v = -1;
		assertEquals(P1.linearSearch(v, arr), expected);
	}
	@Test
	void returnInvalid1() {
		int[] arr = {-3, 4, -1, -1, 0 ,13 ,5};
		int expected = -1;
		int v = 1;
		assertEquals(P1.linearSearch(v, arr), expected);
	}
	@Test
	void returnInvalid2() {
		int[] arr = {3, 4, 1, 1, 0 ,13 ,5};
		int expected = -1;
		int v = 111;
		assertEquals(P1.linearSearch(v, arr), expected);
	}
}
```

The output of the UnitTests is as follows:
![image](https://user-images.githubusercontent.com/123557378/231528990-b6f9f144-21e1-4684-88a7-5c1ebe7bc0a6.png)

| Tester Action and Input Data    | Expected Outcome | Test Case Type           |
| ------------------------------- | ---------------- | ------------------------ |
| arr=[-3,4,-1,1,0,13,5], v = 1   | 3                | Equivalence Partitioning |
| arr=[-3,4,-1,-1,0,13,5], v = -1 | 2                | Equivalence Partitioning |
| arr=[-3,4,-1,-1,0,13,5], v = 1  | -1               | Boundary Value Analysis  |
| arr=[3,4,1,1,0,13,5], v = 111   | -1               | Boundary Value Analysis  |

> **P2.java** contains code to count occurrence of a particular value in an array of integers.

The test cases written for **_countItem(int v, int[] a)_** are as follows

```java
import static org.junit.jupiter.api.Assertions.*;

class P2Test {
	@Test
	void present1() {
		int[] arr = {1,1,2,4,6,6,4,32,1,5,76,2,1};
		int val = 1;
		int count = 4;
		assertEquals(P2.countItem(val, arr), count);
	}
	@Test
	void absent1() {
		int[] arr = {1,2,3,4,5,6,7};
		int val = 0;
		int count = 0;
		assertEquals(P2.countItem(val, arr), count);
	}
	@Test
	void present2() {
		int[] arr = {1,-1,2,4,-6,6,-4,-32,1,5,-76,2,-1};
		int val = 6;
		int count = 1;
		assertEquals(P2.countItem(val, arr), count);
	}
	@Test
	void absent2() {
		int[] arr = {-1,2,-3,4,-5,6,-7};
		int val = -6;
		int count = 0;
		assertEquals(P2.countItem(val, arr), count);
	}
}
```

The output of the UnitTests is as follows:  
![image](https://user-images.githubusercontent.com/123557378/231535978-4606b8be-7b86-45b2-8eeb-a91a2a1d2ad9.png)

| Tester Action and Input Data                   | Expected Outcome | Test Case Type           |
| ---------------------------------------------- | ---------------- | ------------------------ |
| arr=[1,1,2,4,6,6,4,32,1,5,76,2,1], v = 1       | 4                | Equivalence Partitioning |
| arr=[1,2,3,4,5,6,7], v = 0                     | 0                | Boundary Value Analysis  |
| arr=[1,-1,2,4,-6,6,-4,-32,1,5,-76,2,-1], v = 6 | 1                | Boundary Value Analysis  |
| arr=[-1,2,-3,4,-5,6,-7], v = -6                | 0                | Boundary Value Analysis  |

> **P3.java** contains code to perform binary search on a sorted array of integers to find a particular value. Returns _-1_ if value is not found.

The test cases written for **_countItem(int v, int[] a)_** are as follows

```java
import static org.junit.jupiter.api.Assertions.*;

class P3Test {
	@Test
	void findElement1() {
		int[] arr = {0,1,2,3,4,5,6,7};
		assertEquals(P3.binarySearch(4, arr), 4);
	}
	@Test
	void findElement2() {
		int[] arr = {0,1,2,3,7};
		assertEquals(P3.binarySearch(7, arr), 4);
	}
	@Test
	void findElement3() {
		int[] arr = {0,2,4,5,7};
		assertEquals(P3.binarySearch(0, arr), 0);
	}
	@Test
	void absentElement1() {
		int[] arr = {0,1,2,4};
		assertEquals(P3.binarySearch(5, arr), -1);
	}
	@Test
	void absentElement2() {
		int[] arr = {};
		assertEquals(P3.binarySearch(5, arr), -1);
	}
}
```

The output of the UnitTests is as Follows:  
![image](https://user-images.githubusercontent.com/123557378/231538021-0bfbf85f-a3b8-4305-aae1-87306ba93777.png)

| Tester Action and Input Data | Expected Outcome | Test Case Type           |
| ---------------------------- | ---------------- | ------------------------ |
| arr=[0,1,2,3,4,5,6,7], v = 4 | 4                | Equivalence Partitioning |
| arr=[0,1,2,3,7], v = 7       | 4                | Equivalence Partitioning |
| arr=[0,2,4,5,7], v = 0       | 0                | Boundary Value Analysis  |
| arr=[0,1,2,4], v = 5         | -1               | Boundary Value Analysis  |
| arr=[], v = 5                | -1               | Boundary Value Analysis  |

> **P4.java** contains code to check if given measurements are sides of a _SCALENE (2)_, _ISOSCELES (1)_, or an _EQUILATERAL (0)_ triangle. Returns _INVALID (3)_ if given sides cannot form any triangle.

The test cases written for **_triangle(int a, int b, int c)_** iare as follows

```java
import static org.junit.jupiter.api.Assertions.*;

class P4Test {
	@Test
	void invalid1() {
		int a = 0, b = 0, c = 0;
		int expected = P4.INVALID;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void invalid2() {
		int a = 0, b = 5, c = 0;
		int expected = P4.INVALID;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void invalid3() {
		int a = 9, b = 8, c = 0;
		int expected = P4.INVALID;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void invalid4() {
		int a = 9, b = 8, c = 100;
		int expected = P4.INVALID;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void invalid5() {
		int a = -8, b = -8, c = -8;
		int expected = P4.INVALID;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void equilateral1() {
		int a = 10, b = 10, c = 10;
		int expected = P4.EQUILATERAL;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void equilateral2() {
		int a = 100, b = 100, c = 100;
		int expected = P4.EQUILATERAL;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles1() {
		int a = 10, b = 10, c = 12;
		int expected = P4.ISOSCELES;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles2() {
		int a = 12, b = 10, c = 10;
		int expected = P4.ISOSCELES;;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles3() {
		int a = 150, b = 100, c = 150;
		int expected = P4.ISOSCELES;;
		assertEquals(P4.triangle(a, b, c), expected);
	}
	@Test
	void scalene1() {
		int a = 5, b = 6, c = 10;
		int expected = P4.SCALENE;
		assertEquals(P4.triangle(a, b, c), expected);
	}
}
```

The output of the UnitTests is as follows:  
![image](https://user-images.githubusercontent.com/123557378/231539133-e5c53b03-b670-4a96-837a-734dabf1e4f8.png)

| Tester Action and Input Data | Expected Outcome | Test Case Type           |
| ---------------------------- | ---------------- | ------------------------ |
| a = 0, b = 0, c = 0          | INVALID          | Boundary Condition       |
| a = 0, b = 5, c = 0          | INVALID          | Boundary Condition       |
| a = 9, b = 8, c = 0          | INVALID          | Boundary Condition       |
| a = 9, b = 8, c = 100        | INVALID          | Equivalance Partitioning |
| a = -8, b = -8, c = -8       | INVALID          | Boundary Condition       |
| a = 10, b = 10, c = 10       | EQUILATERAL      | Equivalence Partitioning |
| a = 100, b = 100, c = 100    | EQUILATERAL      | Equivalence Partitioning |
| a = 10, b = 10, c = 12       | ISOSCELES        | Equivalence Partitioning |
| a = 12, b = 10, c = 10       | ISOSCELES        | Equivalence Partitioning |
| a = 150, b = 100, c = 150    | ISOSCELES        | Equivalence Partitioning |
| a = 5, b = 6, c = 10         | SCALENE          | Boundary Condition       |

> **P5.java** contains code to check if String _s1_ is a prefix to String _s2_ or not.

The test cases written for **_prefix(String s1, String s2)_** iare as follows

```java
import static org.junit.jupiter.api.Assertions.*;

class P5Test {
	@Test
	void isPrefix1() {
		assertTrue( P5.prefix("", "") );
	}
	@Test
	void isPrefix2() {
		assertTrue(P5.prefix("hell", "hello") );
	}
	@Test
	void isPrefix3() {
		assertTrue(P5.prefix("hell", "hell") );
	}
	@Test
	void isPrefix4() {
		assertTrue(P5.prefix("", "hell") );
	}
	@Test
	void notPrefix1() {
		assertFalse( P5.prefix("hello", "hell"));
	}
	@Test
	void notPrefix2() {
		assertFalse( P5.prefix("he ll", "hell"));
	}
	@Test
	void notPrefix3() {
		assertFalse( P5.prefix(" hell", "hello"));
	}
}
```

The output of the Unittests is as follows:  
![image](https://user-images.githubusercontent.com/123557378/231542386-22753a91-68b5-432f-b4bf-68c8f9604703.png)

| Tester Action and Input Data | Expected Outcome | Test Case Type           |
| ---------------------------- | ---------------- | ------------------------ |
| s1="", s2=""                 | true             | Boundary Condition       |
| s1="hell", s2="hello"        | true             | Equivalence Partitioning |
| s1="hell", s2="hell"         | true             | Boundary Condition       |
| s1="", s2="hell"             | true             | Boundary Condition       |
| s1="hello", s2="hell"        | false            | Equivalence Partitioning |
| s1="he ll", s2="hell"        | false            | Boundary Condition       |
| s1=" hell", s2="hello"       | false            | Boundary Condition       |

---

## Section B
