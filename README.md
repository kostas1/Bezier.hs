Bezier.hs is a very simple demonstration of how simple Bezier curves are, and how
easily you can implement them in Haskell.

For example, to play with the Bezier curve on the four points of the unit square you would run:

    > ghci
    >> :l Bezier.hs
    >> let squareCurve = bezier [[0.0, 0.0], [0.0, 1.0], [1.0, 1.0], [1.0, 0.0]]

And then you can see where the curve is at various points along its
path from t=0 to t=1:

    >> squareCurve 0.0
      [0.0,0.0]
    >> squareCurve 0.25
      [0.15625,0.5625]
    >> squareCurve 0.5
      [0.5,0.75]
    >> squareCurve 0.75
      [0.84375,0.5625]
    >> squareCurve 1.0
      [1.0,0.0]

Alternatively you can use bezierCurve function which works similarly to bezier.
The difference is that instead of specifying a moment in time, you have to specify a number
of points you want from a curve:

    >> bezierCurve [[1, 1], [4, 5], [7, 2]] (4::Float)
      [[1.0,1.0],[3.0,2.8888888],[5.0,3.2222223],[7.0,2.0]]