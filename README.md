# ParallelMatrix

The aim of this project is to implement various optimized algorithm for matrix inversion and multiplication, using the C language and the openMP library.
Simple analytical algorithms for multiplication or inversion (as the row-column product or the inversion using the determinant) are very expensive in terms of memory
and time. This fact is critical when the dimensions of the matrices start to growing. Even with few elements (100x100 matrix and less for the case of the inversion)
a simple C program that implements these simple algortihm risks to be stucked.
In order to analyze and find the right algorithm I have compared 3 matrix multiplication algorithms and 2 matrix inversion algorithms.
## Multiplication Algorithms
The first method implemented is the row-column product. I have wrote this simple algorithm only to compare the performances of this easy-to-use method with more difficult but faster methods.
The second algorithm is the product between a matrix A and the transposition of the matrix B. This method is very similar to the previous way but faster.
The third one is the Strassen's method. This method, the faster among the three, decompose each of the two matrices in 4 squared submatrices. These 8 submatrices are used to compute the final matrix result of the multiplication between the two original matrices. The key of this algorithm is to work with smaller matrices and avoid at most as possible more computational expensive operations as (multiplication between matrices) using addition and subtraction between submatrices.
## Inversion Algorithms
Since the classical Cramer's method for matrix inversion (this method uses computes the disciminant to invert the matrix which is a computational expensive operation with huge matrices) is very unefficient I chose a decomposition strategy to compute this operation. The strategy selected is the LUP decomposition. This algorithm uses a permutation matrix P, a lower triangular matrix L and an upper triangular matrix U. in order to decompose the matrix to be inverted.
## Optimization Strategies
The strategies followed were 2: Parallel For and Division in Task. A common approach of these two strategies was to store the matrix in memory as contiguous monodimensional arrays. This operation is critical when the dimensions grow because it avoids jumps in memory to retrieve matrix's elements.
All the code was divided in function and the loops are parallelized, paying attention to critical sections (i.e. that section of code where the thread wrote on the same variable).


All the tests were computed serially and in parallel form on a Intel i7-4710HQ cpu@2.50 GHz (with 4 physical cores and 4 virtual cores) and using a virtual machine on the Google Cloud Platform with 24 physical cores.\
In the file report.pdf is possible to see the complete analysis of the problem.


