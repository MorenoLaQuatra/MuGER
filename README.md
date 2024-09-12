# Multilingual Generative Error Correction (MuGER)

This repository contains the code for the paper "A Novel Multilingual Benchmark for Post-ASR Generative Error Correction", currently under review.

> [!IMPORTANT]  
> 🚨 The repository is under construction and will be updated with data, code, and instructions after the review process is completed.

### Results

The table below shows the results of the Generative Error Correction models on the MuGER dataset. All results are reported in terms of Word Error Rate (WER). The models are evaluated in three different settings: 
- Top-Hypothesis (baseline): the best hypothesis generated by the ASR system, corresponding to no error correction.
- Zero-Shot: the [Llama 3.1 8B Instruct Model](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct) is prompted to generate the corrected transcription without any example or training.
- ICL: the [Llama 3.1 8B Instruct Model](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct) is prompted to generate the corrected transcription with the help of 5 in-context examples.

We also include the results of the LoRA adaptation of [Llama 3.1 8B Instruct Model](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct) and the [MT5 XL (3B parameters)](https://huggingface.co/google/mt5-xl) model.

The table below shows the results aggregated by language group.

| Language Group |  Whisper-Tiny |           |        | Whisper-Medium |           |       | Whisper-Large-v3 |           |       | Whisper-Large-v3 |          |
|:--------------:|:-------------:|:---------:|:------:|:--------------:|:---------:|:-----:|:----------------:|:---------:|:-----:|:----------------:|:--------:|
|                | Top-Hypotesis | Zero-Shot |   ICL  |  Top-Hypotesis | Zero-Shot |  ICL  |   Top-Hypotesis  | Zero-Shot |  ICL  |      L3-LoRA     | MT5-LoRA |
|       SSA      |     171.65    |   108.77  | 129.58 |      96.46     |   94.95   | 97.53 |       95.93      |   78.15   | 77.20 |       68.88      |   93.65  |
|       CMN      |     159.40    |   92.68   | 100.06 |      58.57     |   60.24   | 57.14 |       46.70      |   46.95   | 41.45 |       37.35      |   32.26  |
|       SA       |     151.15    |   105.40  | 105.51 |      98.73     |   86.88   | 78.63 |       78.43      |   64.28   | 60.04 |       48.58      |   45.63  |
|       EE       |     91.21     |   75.85   |  75.23 |      49.50     |   34.03   | 28.78 |       22.19      |   21.69   | 18.24 |       18.84      |   13.06  |
|       WE       |     76.56     |   62.43   |  63.88 |      27.53     |   28.19   | 24.27 |       21.13      |   22.65   | 19.01 |       19.09      |   15.08  |
|       SEA      |     168.33    |   97.71   |  95.16 |      90.44     |   71.64   | 75.68 |       70.96      |   70.67   | 67.86 |       56.11      |  139.90  |
|       CJK      |     76.72     |   70.39   |  66.72 |      66.28     |   60.45   | 56.10 |       66.67      |   60.28   | 55.94 |       41.45      |   35.69  |
|     Average    |     127.86    |   87.60   |  90.88 |      69.64     |   62.34   | 59.73 |       57.43      |   52.10   | 48.53 |       41.47      |   53.61  |

The table below shows the results for the individual languages.

| Language Group |  Whisper-Tiny |           |       | Whisper-Medium |           |        | Whisper-Large-v3 |           |      | Whisper-Large-v3 |          |
|:--------------:|:-------------:|:---------:|:-----:|:--------------:|:---------:|:------:|:----------------:|:---------:|:----:|:----------------:|:--------:|
|                | Top-Hypotesis | Zero-Shot |  ICL  |  Top-Hypotesis | Zero-Shot |   ICL  |   Top-Hypotesis  | Zero-Shot |  ICL |      L3-LoRA     | MT5-LoRA |
|       af       |     1.440     |   0.962   | 1.017 |     0.4624     |   0.423   | 0.4128 |      0.3315      |    0.31   | 0.28 |      0.2225      |  0.2223  |
|       ar       |     0.687     |   0.600   | 0.600 |     0.2188     |   0.244   | 0.2168 |      0.1579      |    0.19   | 0.16 |      0.1606      |  0.1216  |
|       as       |     1.276     |   1.105   | 1.123 |     1.0883     |   1.211   | 1.0857 |      1.0954      |    1.00   | 0.94 |      0.7232      |  0.7664  |
|       az       |     1.305     |   0.924   | 0.946 |     0.3289     |   0.323   | 0.2881 |      0.2041      |    0.22   | 0.19 |      0.2025      |  0.1419  |
|       be       |     0.990     |   0.756   | 0.733 |     0.6137     |   0.428   | 0.3792 |      0.4362      |    0.31   | 0.27 |      0.2685      |  0.1857  |
|       bg       |     0.932     |   0.778   | 0.842 |     0.2225     |   0.213   | 0.1865 |      0.1314      |    0.14   | 0.12 |      0.1377      |  0.0928  |
|       bn       |     1.415     |   1.057   | 1.092 |     1.0470     |   1.054   | 0.9856 |      0.7468      |    0.62   | 0.57 |      0.4476      |  0.4194  |
|       bs       |     0.874     |   0.777   | 0.798 |     0.2476     |   0.227   | 0.1919 |      0.1303      |    0.15   | 0.13 |      0.1382      |   0.114  |
|       ca       |     0.402     |   0.383   | 0.356 |     0.0754     |   0.121   | 0.0945 |      0.0483      |    0.10   | 0.06 |      0.0786      |  0.0449  |
|       cs       |     0.878     |   0.785   | 0.769 |     0.2155     |   0.219   | 0.1722 |      0.1046      |    0.16   | 0.09 |      0.1076      |  0.0767  |
|       cy       |     2.022     |   1.201   | 1.372 |     0.3675     |   0.405   | 0.3681 |      0.2871      |    0.33   | 0.29 |      0.2967      |  0.2417  |
|       da       |     0.880     |   0.862   | 0.862 |     0.2046     |   0.203   | 0.1840 |      0.1243      |    0.15   | 0.13 |       0.129      |  0.1053  |
|       de       |     0.265     |   0.284   | 0.234 |     0.0653     |   0.106   | 0.0697 |      0.0496      |    0.09   | 0.05 |      0.0646      |  0.0485  |
|       el       |     0.724     |   0.656   | 0.675 |     0.1949     |   0.211   | 0.1802 |      0.1193      |    0.15   | 0.12 |      0.1355      |  0.0892  |
|       en       |     0.125     |   0.137   | 0.150 |     0.0550     |   0.057   | 0.0763 |      0.0510      |    0.07   | 0.05 |       0.061      |  0.0484  |
|       es       |     0.167     |   0.176   | 0.161 |     0.0459     |   0.091   | 0.0488 |      0.0372      |    0.08   | 0.04 |      0.0392      |  0.0364  |
|       et       |     1.015     |   0.957   | 0.933 |     0.3074     |    0.30   | 0.2681 |      0.1849      |    0.21   | 0.17 |      0.1933      |  0.1061  |
|       fa       |     1.502     |   1.013   | 1.063 |     0.4254     |    0.36   | 0.2936 |      0.3206      |    0.30   | 0.22 |      0.1807      |  0.2412  |
|       fi       |     0.608     |   0.573   | 0.530 |     0.1395     |    0.19   | 0.1318 |      0.0781      |    0.15   | 0.09 |      0.1035      |  0.0747  |
|       fr       |     0.367     |   0.383   | 0.339 |     0.0861     |    0.12   | 0.0792 |      0.0634      |    0.10   | 0.06 |      0.0692      |  0.0553  |
|       gl       |     0.631     |   0.488   | 0.424 |     0.2123     |    0.22   | 0.1770 |      0.1327      |    0.16   | 0.12 |      0.1198      |  0.0852  |
|       gu       |     1.474     |   0.971   | 0.959 |     1.1095     |    1.05   | 0.7187 |       0.483      |    0.44   | 0.42 |      0.3842      |  0.3029  |
|       ha       |     1.821     |   0.996   | 1.289 |     1.0049     |    1.21   | 1.0987 |      0.8672      |    0.84   | 0.81 |      0.6841      |  0.5695  |
|       he       |     0.737     |   0.741   | 0.715 |     0.3296     |    0.35   | 0.3287 |      0.2657      |    0.30   | 0.27 |      0.2893      |  0.2279  |
|       hi       |     1.854     |   0.950   | 0.883 |     0.4136     |    0.30   | 0.2575 |      0.3127      |    0.25   | 0.20 |       0.167      |  0.1644  |
|       hr       |     0.860     |   0.741   | 0.753 |     0.1942     |    0.22   | 0.1939 |      0.1127      |    0.15   | 0.12 |      0.1321      |  0.0999  |
|       hu       |     0.945     |   0.847   | 0.841 |     0.2503     |    0.31   | 0.2250 |      0.1412      |    0.23   | 0.14 |      0.1365      |  0.1006  |
|       hy       |     1.289     |   1.099   | 1.127 |     0.6025     |    0.57   | 0.5397 |      0.4444      |    0.43   | 0.39 |       0.366      |  0.2478  |
|       id       |     0.558     |   0.492   | 0.464 |     0.1036     |    0.12   | 0.0920 |      0.0612      |    0.09   | 0.06 |      0.0565      |  0.0493  |
|       is       |     2.126     |   1.076   | 1.371 |     0.5107     |    0.54   | 0.4708 |      0.3237      |    0.34   | 0.31 |      0.3618      |  0.1962  |
|       it       |     0.264     |   0.256   | 0.221 |     0.0443     |    0.11   | 0.0429 |       0.029      |    0.10   | 0.03 |      0.0339      |  0.0278  |
|       ja       |     1.009     |   1.003   | 0.999 |     0.9607     |    1.00   |  0.981 |      0.9831      |    1.01   | 0.98 |      0.6896      |  0.5997  |
|       ka       |     1.406     |   1.072   | 1.083 |     2.9946     |    1.30   |  1.085 |      0.6847      |    0.65   | 0.63 |      0.6217      |  0.4187  |
|       kk       |     4.279     |   1.122   | 1.357 |     0.4998     |    0.48   |  0.433 |      0.3317      |    0.35   | 0.29 |      0.2772      |  0.1759  |
|       km       |     6.401     |   1.748   | 1.441 |     2.3849     |    1.06   |  1.347 |      1.2269      |    1.06   | 1.25 |      1.0766      |  1.3865  |
|       kn       |     1.998     |   1.153   | 1.082 |     1.0932     |    0.94   |  0.954 |      0.6397      |    0.58   | 0.54 |      0.4675      |  0.3758  |
|       ko       |     0.356     |   0.405   | 0.335 |     0.1559     |    0.21   |  0.142 |      0.1284      |    0.19   | 0.13 |      0.1394      |  0.1142  |
|       lb       |     1.522     |   1.073   | 1.146 |     0.9147     |    0.87   |  0.838 |      0.8684      |    0.80   | 0.76 |      0.7055      |   0.643  |
|       ln       |     1.439     |   1.078   | 1.453 |     0.9456     |    0.98   |  1.021 |      0.7256      |    0.73   | 0.68 |      0.3961      |  0.4445  |
|       lo       |     2.007     |   1.138   | 1.208 |     1.1038     |    1.11   |  1.228 |      2.4988      |    1.90   | 1.61 |      0.9823      |  1.8736  |
|       lt       |     1.103     |   0.944   | 0.934 |     0.4233     |    0.41   |  0.372 |      0.2458      |    0.26   | 0.23 |      0.2452      |  0.1458  |
|       lv       |     1.091     |   0.894   | 0.883 |     0.3250     |    0.32   |  0.283 |      0.1897      |    0.20   | 0.18 |      0.1843      |  0.0995  |
|       mi       |     1.032     |   1.054   | 0.965 |     0.8742     |    0.93   |  0.874 |      0.3824      |    0.40   | 0.38 |      0.3005      |   0.266  |
|       mk       |     0.830     |   0.664   | 0.691 |     0.2292     |    0.20   |  0.179 |      0.1511      |    0.15   | 0.13 |      0.1261      |  0.0847  |
|       ml       |     1.423     |   1.111   | 1.087 |     1.1683     |    1.08   |  1.065 |      1.1121      |    0.94   | 1.01 |      0.6908      |  0.8319  |
|       mn       |     2.159     |   1.207   | 1.320 |     1.0583     |    1.11   |  1.139 |       0.84       |    0.83   | 0.81 |      0.7758      |  0.7412  |
|       mr       |     1.460     |   1.070   | 1.142 |      0.91      |    0.76   |  0.672 |      0.8071      |    0.63   | 0.53 |      0.4031      |  0.3864  |
|       ms       |     0.526     |   0.486   | 0.440 |      0.13      |    0.16   |  0.118 |      0.0759      |    0.12   | 0.08 |      0.0718      |  0.0588  |
|       mt       |     1.312     |   1.034   | 1.097 |      0.92      |    0.90   |  0.834 |      0.7496      |    0.73   | 0.69 |      0.6057      |  0.5156  |
|       ne       |     1.624     |   1.241   | 1.239 |      1.14      |    1.02   |  0.818 |      0.9456      |    0.90   | 0.68 |       0.458      |  0.4064  |
|       nl       |     0.507     |   0.490   | 0.466 |      0.10      |    0.12   |  0.090 |      0.0588      |    0.09   | 0.10 |      0.0648      |  0.0476  |
|       oc       |     1.284     |   0.954   | 0.979 |      0.84      |    0.67   |  0.649 |      0.7087      |    0.61   | 0.56 |      0.5988      |   0.495  |
|       pa       |     1.565     |   0.997   | 0.990 |      1.04      |    1.02   |  0.839 |      0.8364      |    0.75   | 0.73 |      0.7148      |  0.6533  |
|       pl       |     0.479     |   0.454   | 0.391 |      0.09      |    0.13   |  0.075 |      0.0484      |    0.10   | 0.06 |      0.0581      |  0.0437  |
|       ps       |     1.212     |   1.152   | 1.422 |      1.00      |    1.22   |  1.323 |      0.8961      |    0.88   | 0.84 |      0.6812      |  0.5888  |
|       pt       |     0.199     |   0.200   | 0.166 |      0.05      |    0.08   |  0.050 |      0.0436      |    0.06   | 0.04 |      0.0492      |  0.0387  |
|       ro       |     0.847     |   0.685   | 0.682 |      0.20      |    0.17   |  0.134 |      0.0916      |    0.11   | 0.08 |      0.0799      |  0.0674  |
|       ru       |     0.301     |   0.301   | 0.246 |      0.08      |    0.12   |  0.081 |      0.0561      |    0.10   | 0.06 |      0.0573      |  0.0503  |
|       sd       |     1.174     |   1.218   | 1.237 |      1.04      |    1.07   |  1.088 |      1.0143      |    0.93   | 0.94 |      0.6181      |  0.6169  |
|       sk       |     0.771     |   0.682   | 0.674 |      0.18      |    0.19   |  0.157 |      0.0936      |    0.11   | 0.08 |       0.101      |  0.0602  |
|       sl       |     0.923     |   0.817   | 0.813 |      0.33      |    0.32   |  0.293 |      0.1892      |    0.19   | 0.17 |      0.1854      |  0.1158  |
|       sn       |     2.316     |   1.357   | 1.939 |      1.11      |    1.36   |  1.314 |      1.1597      |    1.14   | 1.10 |      0.7666      |  0.6172  |
|       so       |     1.670     |   1.114   | 1.185 |      1.06      |    1.05   |  1.265 |      0.8992      |    0.89   | 0.87 |      0.8184      |  0.7215  |
|       sr       |     0.914     |   0.770   | 0.768 |      0.39      |    0.41   |  0.298 |      0.2219      |    0.27   | 0.20 |      0.2053      |  0.2394  |
|       sv       |     0.524     |   0.521   | 0.476 |      0.11      |    0.14   |  0.102 |      0.0732      |    0.11   | 0.09 |      0.0846      |  0.0592  |
|       sw       |     1.430     |   0.998   | 1.080 |      0.52      |    0.48   |  0.466 |      0.3432      |    0.32   | 0.31 |      0.2718      |  0.1902  |
|       ta       |     2.097     |   1.042   | 1.118 |      0.54      |    0.53   |  0.503 |      0.4904      |    0.48   | 0.44 |      0.4204      |  0.3326  |
|       te       |     1.517     |   1.066   | 1.064 |      1.11      |    0.96   |  0.949 |      0.7401      |    0.62   | 0.59 |      0.5934      |  0.4867  |
|       tg       |     1.231     |   1.006   | 1.028 |      0.75      |    0.72   |  0.596 |       0.742      |    0.71   | 0.58 |      0.4549      |  0.3958  |
|       th       |     1.482     |   1.219   | 1.301 |      1.22      |    1.14   |  1.146 |      0.9555      |    0.93   | 0.87 |      0.8309      |  0.7766  |
|       tr       |     0.396     |   0.422   | 0.374 |      0.08      |    0.14   |  0.083 |      0.0561      |    0.12   | 0.06 |      0.0844      |  0.0544  |
|       uk       |     0.528     |   0.479   | 0.467 |      0.12      |    0.13   |  0.101 |      0.0701      |    0.09   | 0.07 |      0.0767      |  0.0553  |
|       ur       |     0.893     |   0.722   | 0.701 |      0.29      |    0.29   |  0.287 |      0.2268      |    0.23   | 0.22 |      0.2278      |  0.1885  |
|       uz       |     1.459     |   1.082   | 1.182 |      1.08      |    1.08   |  1.012 |      0.8666      |    0.80   | 0.70 |      0.6288      |  0.5372  |
|       vi       |     0.652     |   0.648   | 0.656 |      0.13      |    0.16   |  0.140 |      0.0897      |    0.10   | 0.08 |      0.0825      |  0.0721  |
|       yo       |     1.251     |   1.099   | 1.322 |      1.04      |    1.04   |  1.114 |      1.0235      |    1.02   | 0.98 |      0.9006      |    0.9   |

> [!NOTE]
> We plan to release the dataset and the code after the review process is completed. Together we will provide a leaderboard for the MuGER dataset to better navigate the results and include new models.
