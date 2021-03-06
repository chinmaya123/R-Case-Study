# R-Case-Study
R version 3.3.1 (2016-06-21) -- "Bug in Your Hair"
Copyright (C) 2016 The R Foundation for Statistical Computing
Platform: x86_64-apple-darwin13.4.0 (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

  Natural language support but running in an English locale

R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

[R.app GUI 1.68 (7238) x86_64-apple-darwin13.4.0]

[History restored from /Users/Chinmaya/.Rapp.history]

> datacancer=read.csv("/Users/Chinmaya/Downloads/data.csv",stringsAsFactors = FALSE)
> str(datacancer)
'data.frame':	569 obs. of  33 variables:
 $ id                     : int  842302 842517 84300903 84348301 84358402 843786 844359 84458202 844981 84501001 ...
 $ diagnosis              : chr  "M" "M" "M" "M" ...
 $ radius_mean            : num  18 20.6 19.7 11.4 20.3 ...
 $ texture_mean           : num  10.4 17.8 21.2 20.4 14.3 ...
 $ perimeter_mean         : num  122.8 132.9 130 77.6 135.1 ...
 $ area_mean              : num  1001 1326 1203 386 1297 ...
 $ smoothness_mean        : num  0.1184 0.0847 0.1096 0.1425 0.1003 ...
 $ compactness_mean       : num  0.2776 0.0786 0.1599 0.2839 0.1328 ...
 $ concavity_mean         : num  0.3001 0.0869 0.1974 0.2414 0.198 ...
 $ concave.points_mean    : num  0.1471 0.0702 0.1279 0.1052 0.1043 ...
 $ symmetry_mean          : num  0.242 0.181 0.207 0.26 0.181 ...
 $ fractal_dimension_mean : num  0.0787 0.0567 0.06 0.0974 0.0588 ...
 $ radius_se              : num  1.095 0.543 0.746 0.496 0.757 ...
 $ texture_se             : num  0.905 0.734 0.787 1.156 0.781 ...
 $ perimeter_se           : num  8.59 3.4 4.58 3.44 5.44 ...
 $ area_se                : num  153.4 74.1 94 27.2 94.4 ...
 $ smoothness_se          : num  0.0064 0.00522 0.00615 0.00911 0.01149 ...
 $ compactness_se         : num  0.049 0.0131 0.0401 0.0746 0.0246 ...
 $ concavity_se           : num  0.0537 0.0186 0.0383 0.0566 0.0569 ...
 $ concave.points_se      : num  0.0159 0.0134 0.0206 0.0187 0.0188 ...
 $ symmetry_se            : num  0.03 0.0139 0.0225 0.0596 0.0176 ...
 $ fractal_dimension_se   : num  0.00619 0.00353 0.00457 0.00921 0.00511 ...
 $ radius_worst           : num  25.4 25 23.6 14.9 22.5 ...
 $ texture_worst          : num  17.3 23.4 25.5 26.5 16.7 ...
 $ perimeter_worst        : num  184.6 158.8 152.5 98.9 152.2 ...
 $ area_worst             : num  2019 1956 1709 568 1575 ...
 $ smoothness_worst       : num  0.162 0.124 0.144 0.21 0.137 ...
 $ compactness_worst      : num  0.666 0.187 0.424 0.866 0.205 ...
 $ concavity_worst        : num  0.712 0.242 0.45 0.687 0.4 ...
 $ concave.points_worst   : num  0.265 0.186 0.243 0.258 0.163 ...
 $ symmetry_worst         : num  0.46 0.275 0.361 0.664 0.236 ...
 $ fractal_dimension_worst: num  0.1189 0.089 0.0876 0.173 0.0768 ...
 $ X                      : logi  NA NA NA NA NA NA ...
> datacancer$id<-NULL
> datacancer$X<-NULL
> str(datacancer)
'data.frame':	569 obs. of  31 variables:
 $ diagnosis              : chr  "M" "M" "M" "M" ...
 $ radius_mean            : num  18 20.6 19.7 11.4 20.3 ...
 $ texture_mean           : num  10.4 17.8 21.2 20.4 14.3 ...
 $ perimeter_mean         : num  122.8 132.9 130 77.6 135.1 ...
 $ area_mean              : num  1001 1326 1203 386 1297 ...
 $ smoothness_mean        : num  0.1184 0.0847 0.1096 0.1425 0.1003 ...
 $ compactness_mean       : num  0.2776 0.0786 0.1599 0.2839 0.1328 ...
 $ concavity_mean         : num  0.3001 0.0869 0.1974 0.2414 0.198 ...
 $ concave.points_mean    : num  0.1471 0.0702 0.1279 0.1052 0.1043 ...
 $ symmetry_mean          : num  0.242 0.181 0.207 0.26 0.181 ...
 $ fractal_dimension_mean : num  0.0787 0.0567 0.06 0.0974 0.0588 ...
 $ radius_se              : num  1.095 0.543 0.746 0.496 0.757 ...
 $ texture_se             : num  0.905 0.734 0.787 1.156 0.781 ...
 $ perimeter_se           : num  8.59 3.4 4.58 3.44 5.44 ...
 $ area_se                : num  153.4 74.1 94 27.2 94.4 ...
 $ smoothness_se          : num  0.0064 0.00522 0.00615 0.00911 0.01149 ...
 $ compactness_se         : num  0.049 0.0131 0.0401 0.0746 0.0246 ...
 $ concavity_se           : num  0.0537 0.0186 0.0383 0.0566 0.0569 ...
 $ concave.points_se      : num  0.0159 0.0134 0.0206 0.0187 0.0188 ...
 $ symmetry_se            : num  0.03 0.0139 0.0225 0.0596 0.0176 ...
 $ fractal_dimension_se   : num  0.00619 0.00353 0.00457 0.00921 0.00511 ...
 $ radius_worst           : num  25.4 25 23.6 14.9 22.5 ...
 $ texture_worst          : num  17.3 23.4 25.5 26.5 16.7 ...
 $ perimeter_worst        : num  184.6 158.8 152.5 98.9 152.2 ...
 $ area_worst             : num  2019 1956 1709 568 1575 ...
 $ smoothness_worst       : num  0.162 0.124 0.144 0.21 0.137 ...
 $ compactness_worst      : num  0.666 0.187 0.424 0.866 0.205 ...
 $ concavity_worst        : num  0.712 0.242 0.45 0.687 0.4 ...
 $ concave.points_worst   : num  0.265 0.186 0.243 0.258 0.163 ...
 $ symmetry_worst         : num  0.46 0.275 0.361 0.664 0.236 ...
 $ fractal_dimension_worst: num  0.1189 0.089 0.0876 0.173 0.0768 ...
> trainingSet<-datacancer[1:399, 2:31]
> testSet<-datacancer[400:569,2:31]
> trainingOutcomes<-datacancer[1:399,1]
> testOutcomes<-datacancer[400:569,1]
> library(class)
> predictions<-knn(train=trainingSet,cl=trainingOutcomes,k=19,test=testSet)
> predictions
  [1] B M B B B B B M B M B B B B B M B B M B B B B B B B B B B B B B B M M B M
 [38] B B B B B M B B M B M B B M B M B B B B B B B B M M B B B B B B M B B B M
 [75] B B B M B B M B M B B B B B M B M B M M B B B B B M M B M B M B B B B M M
[112] B B M B M B M M B B B M B B B B B B B B B B M M B M B B B B B B B B B B B
[149] B B B B B B B B B B B B B B B M M M M M M B
Levels: B M
> predictions<-gsub("B","benign",predictions)
> predictions<-gsub("M","malignant",predictions)
> predictions
  [1] "benign"    "malignant" "benign"    "benign"    "benign"    "benign"   
  [7] "benign"    "malignant" "benign"    "malignant" "benign"    "benign"   
 [13] "benign"    "benign"    "benign"    "malignant" "benign"    "benign"   
 [19] "malignant" "benign"    "benign"    "benign"    "benign"    "benign"   
 [25] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
 [31] "benign"    "benign"    "benign"    "malignant" "malignant" "benign"   
 [37] "malignant" "benign"    "benign"    "benign"    "benign"    "benign"   
 [43] "malignant" "benign"    "benign"    "malignant" "benign"    "malignant"
 [49] "benign"    "benign"    "malignant" "benign"    "malignant" "benign"   
 [55] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
 [61] "benign"    "malignant" "malignant" "benign"    "benign"    "benign"   
 [67] "benign"    "benign"    "benign"    "malignant" "benign"    "benign"   
 [73] "benign"    "malignant" "benign"    "benign"    "benign"    "malignant"
 [79] "benign"    "benign"    "malignant" "benign"    "malignant" "benign"   
 [85] "benign"    "benign"    "benign"    "benign"    "malignant" "benign"   
 [91] "malignant" "benign"    "malignant" "malignant" "benign"    "benign"   
 [97] "benign"    "benign"    "benign"    "malignant" "malignant" "benign"   
[103] "malignant" "benign"    "malignant" "benign"    "benign"    "benign"   
[109] "benign"    "malignant" "malignant" "benign"    "benign"    "malignant"
[115] "benign"    "malignant" "benign"    "malignant" "malignant" "benign"   
[121] "benign"    "benign"    "malignant" "benign"    "benign"    "benign"   
[127] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
[133] "benign"    "malignant" "malignant" "benign"    "malignant" "benign"   
[139] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
[145] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
[151] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
[157] "benign"    "benign"    "benign"    "benign"    "benign"    "benign"   
[163] "benign"    "malignant" "malignant" "malignant" "malignant" "malignant"
[169] "malignant" "benign"   
> write.csv(predictions,"output.csv")
> getwd()
[1] "/Users/Chinmaya"
