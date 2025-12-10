## 国有h1

![[截屏2024-05-08 16.19.58.png]]
## 国有h0
![[截屏2024-05-08 16.38.47.png]]


## 私有H1
![[截屏2024-05-08 18.53.44.png]]
![[截屏2024-05-08 18.53.58.png]]

## 私有H0
![[截屏2024-05-08 18.54.40.png]]










Family: gaussian 
  Links: mu = identity; sigma = identity 
Formula: roa ~ y1 + y2 + y3 + y4 + y5 + y6 + y7 + y8 + y9 + y10 + y11 + y12 + y13 + y14 + y15 + y16 + y17 + y18 + (1 | industry) + (1 | firm:industry) + (1 | ceo:firm:industry) + (1 | chair:firm:industry) 
   Data: data_nation (Number of observations: 12931) 
  Draws: 4 chains, each with iter = 2000; warmup = 1000; thin = 1;
         total post-warmup draws = 4000

Group-Level Effects: 
~ceo:firm:industry (Number of levels: 4035) 
              Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
sd(Intercept)     2.25      0.08     2.08     2.42 1.00      732     1555

~chair:firm:industry (Number of levels: 3985) 
              Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
sd(Intercept)     2.16      0.08     2.00     2.33 1.00      752     1321

~firm:industry (Number of levels: 1478) 
              Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
sd(Intercept)     2.72      0.10     2.51     2.92 1.00     1233     1974

~industry (Number of levels: 73) 
              Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
sd(Intercept)     1.32      0.19     0.98     1.71 1.00     1458     2071

Population-Level Effects: 
          Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
Intercept     3.50      0.30     2.88     4.07 1.01      657      998
y1           -0.55      0.25    -1.03    -0.06 1.00      805     1358
y2            0.04      0.25    -0.44     0.53 1.00      688     1063
y3            0.96      0.25     0.47     1.46 1.01      631     1157
y4           -0.70      0.25    -1.19    -0.20 1.01      662     1202
y5           -0.10      0.25    -0.58     0.41 1.00      636     1131
y6            0.74      0.26     0.23     1.24 1.00      611      974
y7            0.28      0.26    -0.23     0.78 1.01      599     1143
y8           -0.66      0.26    -1.16    -0.15 1.00      576      886
y9           -0.84      0.26    -1.35    -0.32 1.00      568      917
y10          -1.19      0.26    -1.70    -0.68 1.01      566      784
y11          -2.10      0.26    -2.62    -1.56 1.01      587     1017
y12          -1.45      0.26    -1.97    -0.93 1.00      582      871
y13          -0.99      0.26    -1.50    -0.45 1.00      566      822
y14          -0.78      0.27    -1.30    -0.24 1.01      571      865
y15          -0.85      0.27    -1.38    -0.33 1.01      597      921
y16          -1.37      0.26    -1.90    -0.85 1.00      580      957
y17          -1.19      0.27    -1.72    -0.65 1.00      594      960
y18          -1.79      0.27    -2.33    -1.25 1.01      591      905

Family Specific Parameters: 
      Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
sigma     3.03      0.02     2.98     3.07 1.00     2127     2816

Draws were sampled using sampling(NUTS). For each parameter, Bulk_ESS
and Tail_ESS are effective sample size measures, and Rhat is the potential
scale reduction factor on split chains (at convergence, Rhat = 1).


