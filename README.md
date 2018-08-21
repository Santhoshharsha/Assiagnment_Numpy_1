# Assiagnment_Numpy_1
Assiagnment_Numpy_1

import numpy as np
# Create a input vector
vector = np.array([1,2,3,5])
vector

#1) Write a function so that the columns of the output matrix are powers of the input vector. The order of the powers is determined by the increasing boolean argument. Specifically, when increasing is False, the i-th output column is the input vector raised element-wise to the power of N - i - 1.

def geoProgression(vector,increasing):
    N = len(vector)
    alec = np.zeros(N)
    alec2 = np.zeros(N)
    for vect in vector:
        for i in range(N):
             alec[i] = vect**(N-i-1)
        alec2 = np.column_stack((alec2, alec))
    if(increasing == True):
        return alec2[0:,1:]
    else:
        return alec2[0:,1:].T
