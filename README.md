Download Link: https://assignmentchef.com/product/solved-cs-431-programming-language-concepts-homework-10
<br>
Homework 101 SortingThis part of the homework is similar to homework 9 except that the methodsare curried with the rst parameter being the comparison function.1. Write a method merge_sort: (f: (Int, Int) =&gt; Boolean) (lst: List[Int]) List[Int].that takes a function, a list, and return a sorted list.2. Write a method selection_sort: (f: (Int, Int) =&gt; Boolean) (lst: List[Int]) List[Int]that takes a function, a list and return a sorted list.3. Write a method insertion_sort: (f: (Int, Int) =&gt; Boolean) (lst: List[Int]) List[Int]that takes a function, a list and return a sorted list.2 Vector and matrix operationsThis part of the homework is similar to homework 6 except that you will useScala. Scala has a builtin List class and it has methods map, zip, and reducethat you can use to dene your solution.The following questions are about vectors and matrix. We represent vectorsusing lists. For example, List(2,3,5,4) represents a vector of four integers.We represent a matrix using a list of lists. For example, the matrix

1 2 34 5 6

is written as List( List(1,2,3), List(4, 5, 6) ).1. Write a function vectorAdd: (List[Int], List[Int]) =&gt; List[Int]that add two integer vectors of the same size.For example, vectorAdd (List(1,2,3), List(4,5,6)) should returnList(5, 7, 9).2. Write a function svProduct: (Int, List[Int]) =&gt; List[Int] that mul-tiple an integer with an integer list.For example, svProduct(2, List(1,2,3)) should return List(2,4,6).13. Write a function vmProduct: (List[Int], List[List[Int]]) =&gt; List[Int]that multiple a row vector of size n with a matrix with n rows and mcolumns to produce a vector of size m.For example, vmProduct(List(1,2,3), List(List(1,1), List(2,1), List(3,1)))should return List(14, 6). Or,[1 2 3]241 12 13 135 = 1 [1 1] + 2 [2 1] + 3 [3 1]= [1 1] + [4 2] + [9 3]= [14 6]This function uses the functions svProduct and vectorAdd dened earlier.4. Write a function matrixProduct: (List[List[Int]], List[List[Int]]) =&gt; List[List[Int]]that multiple a mn matrix with a nk matrix to obtain a mk matrix.For example

1 2 31 1 1

241 12 13 135 =

v1v2

=

14 66 3

wherev1 = [1 2 3]241 12 13 135 =

14 6

andv2 = [1 1 1]241 12 13 135 =

6 3

That is,matrixProduct(List(List(1,2,3), List(1,1,1)),List(List(1,1), List(2,1), List(3,1)))= List( List(14, 6), List(6, 3) )This problem will use the function vmProduct dened previously.SubmissionWrite your solution in a le by the name of Hwk10.scala.2TestingUse the following template to test your program.object Hwk10{// your methods go heredef main(args: Array[String]) {val lst = List(5,4,11,2,3,1,0,9)println(merge_sort(_&gt;_)(lst))println(selection_sort(_&gt;_)(lst))println(insertion_sort(_&gt;_)(lst))println(merge_sort(_&lt;_)(lst))println(selection_sort(_&lt;_)(lst))println(insertion_sort(_&lt;_)(lst))val v1 = List(1,2,3)val v2 = List(4,5,6)println(vectorAdd(v1, v2))println(svProduct(2, v1))val m1 = List(List(1,1), List(2,1), List(3,1))println(vmProduct(v1, m1))val m2 = List(List(1,2,3), List(1,1,1))println(matrixProduct(m2, m1))}}You should expect the following output.List(11, 9, 5, 4, 3, 2, 1, 0)List(11, 9, 5, 4, 3, 2, 1, 0)List(11, 9, 5, 4, 3, 2, 1, 0)List(0, 1, 2, 3, 4, 5, 9, 11)List(0, 1, 2, 3, 4, 5, 9, 11)List(0, 1, 2, 3, 4, 5, 9, 11)List(5, 7, 9)List(2, 4, 6)List(14, 6)List(List(14, 6), List(6, 3))3