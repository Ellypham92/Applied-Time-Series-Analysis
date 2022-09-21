
<div id="header" align="center">
  <img width="750" height="450" src="https://user-images.githubusercontent.com/64395120/191584937-bcd0a630-0997-4594-9773-917bbd66baea.png"/>
</div>


# Application of Time Series Analysis

 ### :triangular_ruler: Mathematical validation for a weakly stationary time series

Problem: A time series with a periodic component can be constructed from **xt = U1 sin(2πω0t) + U2 cos(2πω0t)**, where U1 and U2 are independent random variables with zero means and **E(U1^2) = E(U2^2) = σ^2**. The constant ω0 determines the period or time it takes the process to make one complete cycle. Show that this series is weakly stationary with autocovariance function γ(h) = σ2 cos(2πω0h).

:heavy_check_mark: To show the stationarity of xt, we first need to check:

**Mean Function**

= ut 

= E[xt]

= E[U1sin(2πω0t) + U2cos(2πω0t)]

= sin(2πω0t)E[U1] + cos(2πω0t)E[U2] 

= sin(2πω0t) * 0 + cos(2πω0t) * 0     #(since their mean = 0, E[U1]=E[U2]=0)

= 0                                   


**Autocovariance function:**

γ(t, t+h) 

= Cov(xt, xt+h) 

= Cov(U1sin(2πω0t) + U2cos(2πω0t), U1sin(2πω0[t+h])+U2cos(2πω0[t+h])

= Cov(U1sin(2πω0t), U1sin(2πω0[t+h]) + Cov(U1sin(2πω0t),U2cos(2πω0[t+h])

      + Cov(U2cos(2πω0t), U1sin(2πω0[t+h]) + Cov(U2cos(2πω0t),U2cos(2πω0[t+h])

= sin(2πω0t)sin(2πω0[t+h])Cov(U1,U1)          # Cov(U1,U1) = σ^2

    + sin(2πω0t)cos(2πω0[t+h])Cov(U1,U2)      # Cov(U1,U2) = 0
      
    + cos(2πω0t)sin(2πω0[t+h])Cov(U2,U1)      # Cov(U2,U1) = 0
          
    + cos(2πω0t)cos(2πω0[t+h])Cov(U2,U2)      # Cov(U2,U2) = σ^2

= sin(2πω0t)sin(2πω0[t+h])σ^2 + cos(2πω0t)cos(2πω0[t+h])σ^2
               
= {sin(2πω0[t+h] sin(2πω0t)) + cos(2πω0[t+h]) cos(2πω0t)} σ^2

# Using cos(A - B) = sin(A)sin(B) + cos(A)cos(B)

= cos(2πω0[t+h] - 2πω0t) σ^2

= cos(2πω0h)σ^2   


**Since, the mean is constant (0) and the autocovariance (cos(2πω0h)σ^2) depends on only lag(h), we can say that the series is weakly stationary.**


