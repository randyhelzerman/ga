# Geometric Algebra

## Vector spaces and their discontents.

Vector spaces are very useful mathematical abstractions.  But they
seem to have some ragged edges and incomplete spots.

There's two different kind of things: scalars, and vectors.  They seem
to obey differnt rule of addition and multiplication.  You can
multiply scalars and vectors, but not vectors and vectors.

What we want to do is be able to lump vectors, scalars, etc into one
big class which we will call "multivectors".  And we want to be able
to treat all multivectors on the same footing, as it were.  We want to
be able to add and multiply together *any* two multivectors and get a
meaningful and useful result.

For this to be a new theory, there have to be additional axioms, but
we want these new axioms to be consistent with all the other axioms we
have about scalars and vectors.  And we want the result to be free from
any ad-hoc special cases as much as possible.

So we'll proceed as follows: we will first lay out the rules which a
vector space has to follow, and then we'll generalize them to a more
euphonious whole.  Since its a lot easier follwing abstrct discussions
with a concrete example in mind: the 2D Euclidean plane.


### scalars

In our homey Eucliean plane, scalars are just our old friends the real
numbers.  They follow the familer rules of addition and
multiplication, and have the familear warts with reguard to dividing
by zero, etc.

Welll...what is a scalar?  Interesting answer:  its called a scalar
because when you multiply it by a vector it scales the vector.  hm......

1.  The scalars are closed under multiplication and addition, i.e. if
    a and b are both scalars, then a+b and a*b are both also scalars.

2.  Scalar addition and multiplication are symmetric: if a and b are
    sclars, then:

            a+b = b+a
            a*b = b*a

3.  Scalar addition and multiplication are associative: if a,b, and c
    are scalars, then:

    a+(b+c) = (a+b)+c = a+b+c
    a*(b*c) = (a*b)*c = a*b*c

Scalar addition and multiplication interact with each other
according to the following axioms:

4.  Distributivity:  if a,b, and c are scalars, then
    a*(b+c) = a*b + a*c

From the the closure of scalars under addition and subtraction, we
conclude that a*(b+c) is a scalar.  And from the symmetry of scalar
multiplication, we can conclude that (b+c)a = b*a + c*a, i.e. we have
both left and right distributivity.

In short, scalars are said to form a *field*.


### Vectors

Vectors are not scalars, and this difference is reflected in the fact
that vectors are not as constrained by the axioms as scalars are.

1.  Vector addition is symmetric: if a and b are vectors, then

    a+b = b+a

2.  Scalar on vector multiplication is symmetric: if a is a scalar,
    and v is a vector, then:

    a*v = v*a
    and the result is a vector.

In other respects, vector addition and multiplication are familier.

### Linear combination of vectors

We form a linear combination of vectors by scaling each vector and
adding the results together.

You can get to any point P from any other point O by some linear
combination of vectors.  But not from other sets of vectors :-)

Definition: Linearly independance:
Suppose you have some vectors v1,....,vn-1.
If vn cannot be expressed as some linear combination
of v1,......,vn-1, then vn is linearly independent of
v1,....,vn-1.


##  Extension of Operations

Now we want to be able to extend the operations of + and * to all
possible pairs of multivectors.  We first discuss addition, and then
we discuss subtraction.


####  Addition

First odd thing; what is the addition of a scalar a and a vector v?
Wierdness.  But we have a ready-made exemplar of what we could
do....what is 1 + the square root of -1?  Basically, we use the same
dodge that complex numbers use, viz, if we are adding two putatively
incommensurate multivectors, we just leave the addition unsimplified,
i.e. the sum of the scalar a and the vector v is just a + v.

Incidentally, this solves the problem of writing out vectors in ascii.
Instead of trying to depict columns of numbers, we can just represent
the vectors as some linear combination of the good old familier basis
vectors, i.e. instad of:

[ x ]
[ y ]

or [x y]^T, we can just write the vectors as:

x*e1 + y*e2


Once we make this move, addition and subtraction of multivectors
is quite a bit like addition and subtraction of polynomials.
We just need to keep together all of the e1 terms and the e2 terms.


2.  Addition is commutative and associative
    a+b = b+a

    (a + b) + c = a + (b + c) = a + b + c


Note that if we are adding two multivectors which happen to be
scalars, then its just good old fashioned real number addition.
In fact, we can consider + to be the same operation no matter
what multivectors are plugged into it.

This satisfies one of our goals we had at the outset: of "rounding
out" the operations.  We no longer have two different addition
operations, one for scalars, and one for vectors.  There's just one
addition operation and it can take as operands *any* two multivectors.
Much neater.


#### Multiplication

Now we want to similarly generalize and unify the multiplication
operations.  One thing we're not going to have is associativity of
multiplication.  a*b is not going to be the same as b*a in general.
Because we are familier with matrix multiplication, we were kind of
expecting that.

Lets list out some properties we'd like this multiplication operation
to have, and then see where they lead us.


2.5  Multiplicative identity
     There exists a multivector 1 such that:
     1 * m = m
     for all multivectors m.

     For our example in the euclidean plane, the scalar 1 is our multiplicative
     identity.  Some examples:

     1 * (5+2e1) = 5+2e1

2.6  Scalar by mulitivector multiplication is commutative

     Since we want this new multiplication to be the same as our old
     multiplications as far as posible, we want a scalar times a
     vector multiplication to be communtative, i.e. a*(x*e1 + y*e2) =
     (x*e1 + y*e2)*a = a*x*e1 + a*y*e2

     This means that left and right multiplicative idenity are the
     same (they are both 1).


3.  Multiplication is associative:

    a*(b*c) = (a*b)*c = a*b*c

4.  Contraction: For any multivector a, a^2 is a scalar.  But which
    scalar?  If you have assigned a metric to your vector space, then
    that is an obvious candidate :-)

    For our Euclidean plane, the metric (as defined on two vectors) is
    the square root of the dot product.

5.  Multiplication distributes over addition

    A*(B+C) = A*B + A*C

   (B+C)*A = BA + CA


##   Decomposing Multiplicatoin

Now, we don't have commutative multiplication in general.  However, we
can "decompose" any multiplication into a sum of two components.  a
symmetric component and an antisymmetric component.


a*b = 1/2 (a*b + a*b)

a*b = (1/2 a*b  + 1/2 a*b) +  (1/2 b*a  - 1/2 b*a)

a*b = (1/2 a*b  + 1/2 b*a) +  (1/2 a*b - 1/2 b*a)

a*b = 1/2(a*b + b*a) + 1/2(a*b - b*a)


###  Symmetric component of multiplication

1/2(a*b + b*a).  As it were, the average of a*b and b*a.  What can we
say about this quantity?  Well, we are at a very high level of
genrality here, but nevertheless the axioms do give us something to go
on.  Is there another context in which we would see the sum a*b + b*a?

Sure, what if we were multiplying (a+b) and (a+b) together?  Well, by
distribution of multiplication over addtion we would get:

(a+b) * (a+b) = a*a + b*b + a*b + b*a

By contraction, we know that (a+b)^2 has to be a scalar.
Additionally, a^2 and b^2 have to be scalars.  This means that the
symmetric sum of products:

a*b + b*a

also has to be a scalar. Bingo. 1/2(a*b + b*a) also has to be a scalar
then.

Because of the contractive nature of this component of multiplication,
we call it the "inner product" and denote it (spoiler alert) with a
dot "."

Definition Inner product of a and b:
The inner product of a and b is:
a . b = 1/2(a*b + b*a)

Note that a.a = 1/2(a*a + a*a), i.e. is equal to the metric.


### non-symmetric component of multiplication

The other component of multiplication we'll call the
"outer product":

Definition: Outer product of a and b:
The outer product of a and b:

a ^ b = 1/2(a*b - b*a)

What can we say about it?  Well, it isn't symetric like the
inner product is.  However, it is antisymmetric.


1/2(a*b - b*a) + 1/2(b*a - a*b)
1/2*a*b - 1/2*b*a + 1/2*b*a - 1/2*a*b
(1/2*a*b- 1/2*a*b) + (1/2*b*a - 1/2*b*a)

-

So a^b = -b^a

###  Properties of the wedge product:


#### Wedge product is antisymmetric

a^b = -b^a

#### Zero when identical

(Follows immediately from the previous property)

a^a = 0


#### The wedge product of two colinear vectors is zero.

a ^ k*a = 1/2*(a*k*a - k*a*a) = 0


#### The colinear contributions to a vector are rejected:


a^(k*a + b) = 1/2(a*(k*a + b) - (k*a + b)*a)
            = 1/2(k*a*a +a*b - k*a*a - b*a)



#### Linear on first and second variables

u^(v+w)= u^v + u^w

(u+w)^v = u^v + w^v


#### Wedge product is associative

u^(v^w) = (u^v)^w = u^v^w


#### Lagrange identity

|u|*|u| * |v|*|v| = (u.v)*(u.v) - (u^v)*(u^v)


####  relations to determinants

If you wedge together all the columns of a square matrix, the
coefficient of the pseudoscalar will be the determinate of the matrix.


##  Inverse of the vector product -- vector division

We need 2 of these: left division and right division

v*u = v.u + v^u

1/a = a/|a|/|a}


##  Representations of various geometric objects

###  Points:

     vectors?  Homogenious vectors?


###  Planes

     A plane going through three points r0, r1, and r2:

     If x is a point on the plain, then:

    (r2-r0)^(r1-r0)^(x-r0) = 0

    A plane with bivector U through point a:

    x^U = a^U


##  Operations


###  Projection and rejection

     If u is a unit vector,

     v = (v.u)*u + (v^u)*u


     (v.u)*u is the projection of v onto u

     (v^u)*u is the rejection of v from u


### Concrete example 2d space


Let e1 and e2 be a basis for the space.


let x = x1*e1 + x2*e2
    y = y1*e1 + y2*e2


x*y = (x1*e1 + x2*e2) * (y1*e1 + y2*e2)

x*y = x1*y1*e1*e1 + x2*y2*e2*e2 + x1*y2*e1*e2 + x2*y1*e2*e1


So, to find out what the general product is, we need to find out:

1.  what is e1*e1
2.  what is e2*e2
3.  what is e1*e2
4.  what is e2*e1?

These are constrained by the contraction axiom, and can
be elucidated by looking at the square of a vector:

a = a1*e1 + a2*e2


a*a = a1*a1*e1*e1 + a2*a2*e2*e2 + a1*a2*e1*e2 + a1*a2*e2*e1

The contraction theorem says that a*a, e1*e1, and e2*e2
all have to be scalars:



---      ----------    -----------
scalar   scalar         scalar

Therefore a1*a2*e1*e2 + a1*a2*e2*e1 also has to be a scalar.
Moreover, if we are using a euclidean norm,


e1*e1 = 1
e2*e2 = 1
(because the lengths of these vectors are one)

Plugging in, we get:

a*a    = a1*a1 + a2*a2 + a1*a2*(e1*e2 + e2*e1)
         -------------
         dot product


Because the underlined portion is the dot product, the rest of the
right hand side has to be equal to zero:

a1*a2*(e1*e2 + e2*e1) = 0


e1*e2 + e2*e1 = 0

This means that e1 and e2 anticommute, i.e:

e1*e2 = - e2*e1


Going back to multiplying (x+y)*(x+y), we can now
plug in:


x*y = x1*y1*e1*e1 + x2*y2*e2*e2 + x1*y2*e1*e2 + x2*y1*e2*e1


x*y = x1*y1 + x2*y2   +   x1*y2*e1*e2 - x2*y1*e1*e2



x*y = x1*y1 + x2*y2   +   (x1*y2 - x2*y1) * e1*e2
      -------------       -------------------------
      this is the dot     this is something else :-)
      product

x*y = x.y + x^y
`

Hmm...looks like multiplication of complex numbers.  Wait, it is
multiplication of complex numbers!

e1*e2 * e1*e2

-e1*(e2*e2)*e1

- e1*e1

-1

The square of e1*e2 is -1.

woooowoowowoowo

###  Properties of the dot product.

This is basically our old familier dot product.  Since a*a is a
scalar, and is equal to:

a.a + a^a

and since a^a is equal to 0, that means that a*a = a.a.

This tells us which scalar a*a should be equal to: it should be equal
to the square of the norm for the particular space you are working
with.


# k-Blades

An outer product of k linearly independant vectors is called a blade.


## How does GA work?

Geometric operations on subspaces and parallelipipeds are represented
by algebraic operations on blades.


##  Operations


###  Rotation

###  Orthogonal Complement

Let b be a blade which represents a subspace.  Then b* = b/I which is
the orthogonal complement of b.

e1e2 + e2e3 + e1e3

what is this the outer product of?

b1^b2 = e1e2 + e2e3 + e1e3

b1^b2 = e1e2 + e1e3 + e2e3


b1^b2 = e1^(e2 + e3) + e2e3
