# 1 dimention:

moving:  real number addition.
rotating:  multiply by -1:


## 2  dimensions:

moving: complex number addition.
rotating: multiply by a comlex number which has magnitude of 1:

## 3 dimensions:

Need quaternions :-)



#  Quaternion

## can you add a vector and a scalar?

a + bi +cj +dk

i^2 = -1
j^2 = -1
k^2 = -1

ijk = -1


## Quaternion addition

Just add componentwise


##  Derive the multiplication table:


  |   i   j   k
--+-------------
i |  -1  -k   j
  |
j |   k  -1  -i
  |
k |  -j   i  -1



##  we already know the diagonals

i^2 = -1
j^2 = -1
k^2 = -1


##  From the other axiom, we can derive the rest.

###   i * j


ijk = -1

ijk * k = -1 * k

ij * -1 = -k

ij = k


###  j * k


i * ijk = i * -1

jk = i


###  j * j

ijk = -1

ijk * kj = -kj

i = -kj


###  j*i

jk = -1

ji * ijk = -ji

ji = -k


###  ik

i * i * j = i * k

-j = i*k


YEAH BUT WHAT DOES IT MEAN


# Rotation


v = (v1,v2,v3)
p = (x,y,z)


h= a + bi + cj + dk
h* = a - bi - cj - dk

a = cos(t/2)
b = v1 sin(t/2)
c = v2 sin(t/2)
d = v3 sin(t/2)

p' = h p h*