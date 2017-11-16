. *// Added log using command

. log using \\Client\C$\Users\lg\Desktop\STATA\seungkilee_exam2.log

       name:  Seung Ki Lee
       log:  \\Client\C$\Users\lg\Desktop\STATA\seungkilee_exam2.log
  log type:  text
 opened on:  15 Nov 2017, 16:59:46

. use "\\Client\C$\Users\lg\Desktop\STATA\hprice1.dta"

. regress price lotsize sqrft bdrms assess

      Source |       SS           df       MS      Number of obs   =        88
------------- + ----------------------------------   F(4, 83)        =    100.74
       Model |  761089.801         4   190272.45   Prob > F        =    0.0000
    Residual |  156764.704        83  1888.73138   R-squared       =    0.8292
-------------+----------------------------------   Adj R-squared   =    0.8210
       Total |  917854.506        87  10550.0518   Root MSE        =     43.46
       price |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
     lotsize |   .0005867   .0004963     1.18   0.240    -.0004004    .0015738
       sqrft |  -.0005175   .0170849    -0.03   0.976    -.0344986    .0334636
       bdrms |   11.60249   6.549515     1.77   0.080    -1.424233    24.62921
      assess |   .9082991   .1040386     8.73   0.000     .7013706    1.115228
       _cons |  -38.88702   21.49853    -1.81   0.074    -81.64673    3.872696
------------------------------------------------------------------------------

.
. regress price lotsize sqrft bdrms assess, beta

      Source |       SS           df       MS      Number of obs   =        88
-------------+----------------------------------   F(4, 83)        =    100.74
       Model |  761089.801         4   190272.45   Prob > F        =    0.0000
    Residual |  156764.704        83  1888.73138   R-squared       =    0.8292
-------------+----------------------------------   Adj R-squared   =    0.8210
       Total |  917854.506        87  10550.0518   Root MSE        =     43.46
       price |      Coef.   Std. Err.      t    P>|t|                     Beta
     lotsize |   .0005867   .0004963     1.18   0.240                 .0581177
       sqrft |  -.0005175   .0170849    -0.03   0.976                -.0029079
       bdrms |   11.60249   6.549515     1.77   0.080                 .0950435
      assess |   .9082991   .1040386     8.73   0.000                 .8428694
       _cons |  -38.88702   21.49853    -1.81   0.074                        .
------------------------------------------------------------------------------

.
. generate sqrftbdrms = sqrft*bdrms

.
. regress price lotsize sqrft bdrms assess sqrftbdrms

      Source   |       SS           df       MS      Number of obs   =        88
-------------+----------------------------------   F(5, 82)        =     82.92
       Model   |  766291.045         5  153258.209   Prob > F        =    0.0000
    Residual   |  151563.461        82  1848.33489   R-squared       =    0.8349
-------------+----------------------------------   Adj R-squared   =    0.8248
       Total   |  917854.506        87  10550.0518   Root MSE        =    42.992
       price   |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
     lotsize   |   .0005909    .000491     1.20   0.232    -.0003858    .0015676
       sqrft   |  -.0459807   .0319399    -1.44   0.154    -.1095193    .0175578
       bdrms   |  -14.66388   16.94556    -0.87   0.389      -48.374    19.04625
      assess   |   .8802809   .1042664     8.44   0.000     .6728617      1.0877
    sqrftbdrms |   .0120843   .0072038     1.68   0.097    -.0022462    .0264149
       _cons   |   65.28181   65.63846     0.99   0.323      -65.294    195.8576
.
. regress lprice lassess llotsize lsqrft bdrms

      Source |       SS           df       MS      Number of obs   =        88
-------------+----------------------------------   F(4, 83)        =     70.58
       Model |  6.19607473         4  1.54901868   Prob > F        =    0.0000
    Residual |  1.82152879        83   .02194613   R-squared       =    0.7728
-------------+----------------------------------   Adj R-squared   =    0.7619
       Total |  8.01760352        87  .092156362   Root MSE        =    .14814
      lprice |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
     lassess |   1.043065    .151446     6.89   0.000     .7418453    1.344285
    llotsize |   .0074379   .0385615     0.19   0.848    -.0692593    .0841352
      lsqrft |  -.1032384   .1384305    -0.75   0.458     -.378571    .1720942
       bdrms |   .0338392   .0220983     1.53   0.129    -.0101135    .0777918
       _cons |    .263743   .5696647     0.46   0.645    -.8692972    1.396783


. use "\\Client\C$\Users\lg\Desktop\STATA\hprice1.dta", clear

. xi : regress lprice lassess llotsize lsqrft i.bdrms
i.bdrms           _Ibdrms_2-7         (naturally coded; _Ibdrms_2 omitted)

       Source |       SS           df       MS      Number of obs   =        88
-------------+----------------------------------   F(8, 79)        =     37.86
        Model |  6.35910406         8  .794888008   Prob > F        =    0.0000
     Residual |  1.65849946        79  .020993664   R-squared       =    0.7931
-------------+----------------------------------   Adj R-squared   =    0.7722
        Total |  8.01760352        87  .092156362   Root MSE        =    .14489
       lprice |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
-------------+----------------------------------------------------------------
      lassess |   .9594261   .1542371     6.22   0.000     .6524248    1.266427
     llotsize |   .0198889   .0386145     0.52   0.608    -.0569715    .0967492
       lsqrft |  -.0342931   .1436377    -0.24   0.812    -.3201967    .2516105
    _Ibdrms_3 |   .0816087   .0802862     1.02   0.313     -.078197    .2414143
    _Ibdrms_4 |   .0422334   .0830461     0.51   0.612    -.1230657    .2075326
    _Ibdrms_5 |   .1879371   .1047448     1.79   0.077    -.0205522    .3964265
    _Ibdrms_6 |   .3489299   .1641039     2.13   0.037     .0222892    .6755705
    _Ibdrms_7 |   .1956565   .1767382     1.11   0.272     -.156132     .547445
        _cons |   .1538384   .6415412     0.24   0.811    -1.123117    1.430794



. use "\\Client\C$\Users\lg\Desktop\STATA\charity.dta"

. regress respond avggift propresp resplast

      Source |       SS           df       MS      Number of obs   =     4,268
-------------+----------------------------------   F(3, 4264)      =    360.76
       Model |  207.349397         3  69.1164656   Prob > F        =    0.0000
    Residual |  816.930594     4,264   .19158785   R-squared       =    0.2024
-------------+----------------------------------   Adj R-squared   =    0.2019
       Total |  1024.27999     4,267  .240046869   Root MSE        =    .43771
------------------------------------------------------------------------------
     respond |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
     avggift |    .000182   .0000852     2.14   0.033     .0000151     .000349
    propresp |   .7486844   .0336928    22.22   0.000      .682629    .8147397
    resplast |   .0946678   .0180867     5.23   0.000     .0592085    .1301271
       _cons |    .002304   .0151179     0.15   0.879     -.027335    .0319431

. regress respond avggift propresp resplast, robust

Linear regression                               Number of obs     =      4,268
                                                F(3, 4264)        =     437.21
                                                Prob > F          =     0.0000
                                                R-squared         =     0.2024
                                                Root MSE          =     .43771
    
             |               Robust
     respond |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
     avggift |    .000182   .0000302     6.03   0.000     .0001228    .0002412
    propresp |   .7486844   .0339127    22.08   0.000     .6821978    .8151709
    resplast |   .0946678   .0200048     4.73   0.000     .0554479    .1338877
       _cons |    .002304   .0134189     0.17   0.864    -.0240039     .028612


. use "\\Client\C$\Users\lg\Desktop\STATA\FERTIL2.DTA"

. regress children agefbrth heduc electric urban frsthalf

      Source |       SS           df       MS      Number of obs   =     1,829
-------------+----------------------------------   F(5, 1823)      =     49.90
       Model |  1045.55915         5  209.111829   Prob > F        =    0.0000
    Residual |  7639.66775     1,823  4.19071188   R-squared       =    0.1204
-------------+----------------------------------   Adj R-squared   =    0.1180
       Total |   8685.2269     1,828  4.75121822   Root MSE        =    2.0471
------------------------------------------------------------------------------
    children |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
    agefbrth |  -.0870396   .0150396    -5.79   0.000    -.1165362    -.057543
       heduc |  -.1063142   .0116707    -9.11   0.000    -.1292036   -.0834248
    electric |   .1769759   .1486607     1.19   0.234    -.1145873    .4685391
       urban |  -.6126852    .105892    -5.79   0.000    -.8203675   -.4050028
    frsthalf |   .1585793   .0976347     1.62   0.105    -.0329084     .350067
       _cons |   6.107631   .2969519    20.57   0.000     5.525229    6.690033

. estat hettest

Breusch-Pagan / Cook-Weisberg test for heteroskedasticity
         Ho: Constant variance
         Variables: fitted values of children
    
         chi2(1)      =    70.16
         Prob > chi2  =   0.0000

.
. estat hettest, fstat

Breusch-Pagan / Cook-Weisberg test for heteroskedasticity
         Ho: Constant variance
         Variables: fitted values of children
    
         F(1 , 1827)  =    64.08
         Prob > F     =   0.0000

.
. predict e, residual
(2,532 missing values generated)

.
. generate loge2 = log(e^2)
(2,532 missing values generated)

.
. regress loge2 agefbrth heduc electric urban frsthalf

      Source |       SS           df       MS      Number of obs   =     1,829
-------------+----------------------------------   F(5, 1823)      =     11.87
       Model |  280.992152         5  56.1984304   Prob > F        =    0.0000
    Residual |  8629.10876     1,823  4.73346613   R-squared       =    0.0315
-------------+----------------------------------   Adj R-squared   =    0.0289
       Total |  8910.10091     1,828  4.87423463   Root MSE        =    2.1757
       loge2 |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
    agefbrth |  -.0207735   .0159838    -1.30   0.194    -.0521221    .0105751
       heduc |  -.0505752   .0124035    -4.08   0.000    -.0749017   -.0262487
    electric |  -.4106443   .1579945    -2.60   0.009    -.7205134   -.1007751
       urban |  -.1071428   .1125405    -0.95   0.341    -.3278646     .113579
    frsthalf |   .0726184   .1037648     0.70   0.484     -.130892    .2761288
       _cons |   .9293377   .3155962     2.94   0.003     .3103695    1.548306
------------------------------------------------------------------------------

.
. predict yhat, xb
(2,532 missing values generated)

.
. generate hhat = exp(yhat)
(2,532 missing values generated)

.
. generate invhat = 1/hhat
(2,532 missing values generated)

.
. wls0 children agefbrth heduc electric urban frsthalf, wvar(invhat) type(abse)
(2,532 missing values generated)
(2,532 missing values generated)

WLS regression -  type: proportional to abs(e)

(sum of wgt is   8.6693e+02)

      Source |       SS           df       MS      Number of obs   =     1,829
-------------+----------------------------------   F(5, 1823)      =     86.23
       Model |  1415.86684         5  283.173368   Prob > F        =    0.0000
    Residual |   5986.7457     1,823  3.28400751   R-squared       =    0.1913
-------------+----------------------------------   Adj R-squared   =    0.1890
       Total |  7402.61254     1,828  4.04956922   Root MSE        =    1.8122
    children |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
    agefbrth |  -.0586951   .0111472    -5.27   0.000    -.0805578   -.0368325
       heduc |  -.0899087   .0101908    -8.82   0.000    -.1098955   -.0699218
    electric |    .122023   .1259765     0.97   0.333    -.1250504    .3690963
       urban |  -.5182014   .1041625    -4.97   0.000    -.7224918   -.3139109
    frsthalf |   .1552382   .0883906     1.76   0.079    -.0181193    .3285957
       _cons |   5.444577   .2248614    24.21   0.000     5.003564     5.88559
(2,532 missing values generated)

.
. estat hettest

Breusch-Pagan / Cook-Weisberg test for heteroskedasticity
         Ho: Constant variance
         Variables: fitted values of children
    
         chi2(1)      =   246.77
         Prob > chi2  =   0.0000

.
. estat hettest, fstat

Breusch-Pagan / Cook-Weisberg test for heteroskedasticity
         Ho: Constant variance
         Variables: fitted values of children
    
         F(1 , 1827)  =   187.21
         Prob > F     =   0.0000

.
. regress children agefbrth heduc electric urban frsthalf, robust

Linear regression                               Number of obs     =      1,829
                                                F(5, 1823)        =      58.82
                                                Prob > F          =     0.0000
                                                R-squared         =     0.1204
                                                Root MSE          =     2.0471
    
             |               Robust
    children |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
    agefbrth |  -.0870396   .0137216    -6.34   0.000    -.1139513   -.0601279
       heduc |  -.1063142   .0108055    -9.84   0.000    -.1275067   -.0851218
    electric |   .1769759   .1302748     1.36   0.174    -.0785277    .4324795
       urban |  -.6126852   .1055862    -5.80   0.000    -.8197678   -.4056025
    frsthalf |   .1585793   .0967153     1.64   0.101    -.0311051    .3482636
       _cons |   6.107631   .2791021    21.88   0.000     5.560237    6.655024
------------------------------------------------------------------------------

. log close
      name:  Seung Ki Lee
       log:  \\Client\C$\Users\lg\Desktop\STATA\seungkilee_exam2.log
  log type:  text

closed on:  15 Nov 2017, 17:06:33