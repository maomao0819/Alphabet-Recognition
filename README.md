# 以筆跡偵測字母輸入
## Abstract
希望透過筆順、位移、轉角角度物理數據等判別字母。
## Motivation
## Data
### Data Collection
#### Tool
* 自己寫的小畫家
* 紀錄路徑
* 大寫英文字母
#### Data
* About 760 records
* Each letter has about 25 records.
#### Statistics
### Data Preprocessing
#### Problem — Number of Dimension
* The number of samples of each stroke is different.
* The number of strokes of each letter is different.
#### Features of each letter
* The upper bound of the number of strokes of each letter is 4.
* Zero-padding for those # of strokes is lower than 4.
* [Letter][Stroke#1][Stroke#2][Stroke#3][Stroke#4]
#### Features of each stroke
* 角度
* 位移長度
* 路徑長度
* 路徑長相較位移長之倍率
* 該筆劃之起點相較第一筆劃起點之距離
* 斜率於X軸上變號之次數
* 斜率於Y軸上變號之次數
#### Stroke
* One-stroke letter is hard to identify by feature 1 to 5.
* Feature 6 and feature 7 to identify the change of slope.
#### Enhancement
Angle is the most important feature, so sign-square itself to enhance it.
#### Normalization
The size of bounding box of each record may be different.
## Results
### Data Preprocessing
### Model – KNN
* Accuracy :  0.96
* B-P 
* D-K
* E-I
* P-D
* K-R
### Model - Random Forest
* Accuracy : 1.00 
* D-P 
### Model – SVM
* Accuracy : 0.92
* D-P
* K-R 
* C-U
* V-X
### Mondel – ANN
* Accuracy : 0.97 
* D-P
* J-T
* J-X
## Conclusion
* Only need 28 features for each data
* Accuracy is high
* D-P is hard to identify
* Not very general
* Highly depends on user
