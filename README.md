# ParallelMatrix

The aim of this project is to implement various optimized algorithm for matrix inversion and multiplication, using the C language and the openMP library.
Simple analytical algorithms for multiplication or inversion (as the row-column product or the inversion using the determinant) are very expensive in terms of memory
and time. This fact is critical when the dimensions of the matrices start to growing. Even with few elements (100x100 matrix and less for the case of the inversion)
a simple C program that implements these simple algortihm risks to be stucked.
In order to analyze and find the right algorithm I have compared 3 matrix multiplication algorithms and 2 matrix inversion algorithms.
## Multiplication algorithms
The first method implemented is the row-column product. I have wrote this simple algorithm only to compare the performances of this easy-to-use method with more difficult but faster methods.
The second algorithm is the product between a matrix A and the transposition of the matrix B. This method is very similar to the previous way but faster.
The third one is the Strassen's method. This method, the faster among the three, decompose each of the two matrices in 4 squared submatrices. These 8 submatrices are used to compute the final matrix result of the multiplication between the two original matrices. \
In the file report.pdf is possible to see the complete analysis of the problem.


