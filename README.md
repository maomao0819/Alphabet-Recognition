# 以筆跡偵測字母輸入
## Abstract
希望透過筆順、位移、轉角角度物理數據等判別字母。
## Motivation
![](https://user-images.githubusercontent.com/43957213/126810336-ddc9b31e-3da1-4379-bac0-7c59d9ae640e.png)
## Data
### Data Collection
#### Tool
* 自己寫的小畫家
* 紀錄路徑
* 大寫英文字母

![](https://user-images.githubusercontent.com/43957213/126810338-e47ef1f7-0bba-45ee-b816-81cac5c9f6c2.png)
#### Data
* About 760 records
* Each letter has about 25 records.
#### Statistics
![](https://user-images.githubusercontent.com/43957213/126810341-9d1d1257-3c1c-4577-a773-03a937233bac.png)
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
![](https://user-images.githubusercontent.com/43957213/126810345-81373868-b804-4565-a5f1-51f18ec32ab6.png)
* One-stroke letter is hard to identify by feature 1 to 5.
* Feature 6 and feature 7 to identify the change of slope.
![](https://user-images.githubusercontent.com/43957213/126810348-4c88f9f1-641a-408a-8b6e-697c50432289.png)
#### Enhancement
Angle is the most important feature, so sign-square itself to enhance it.
![](https://user-images.githubusercontent.com/43957213/126810350-9deb9fef-d952-4bee-96c0-089ba9a267da.png)
#### Normalization
The size of bounding box of each record may be different.

![ ](https://user-images.githubusercontent.com/43957213/126810359-24252219-2e5c-4097-b74c-821f8b91d0eb.png)
## Results
### Data Preprocessing
![](https://user-images.githubusercontent.com/43957213/126810362-2bd03e87-8e1b-48c4-a731-078254320a76.png)
### Model – KNN
* Accuracy :  0.96
* B-P 
* D-K
* E-I
* P-D
* K-R

![](https://user-images.githubusercontent.com/43957213/126810367-b0e65de1-89f0-498b-8e35-f1597a407c94.png)
### Model - Random Forest
* Accuracy : 1.00 
* D-P 

![](https://user-images.githubusercontent.com/43957213/126810370-5f51d596-b9d6-48f0-82c5-dbcf08a50082.png)
### Model – SVM
* Accuracy : 0.92
* D-P
* K-R 
* C-U
* V-X

![](https://user-images.githubusercontent.com/43957213/126810373-4958e773-0c51-4c38-be49-52e2a59347cb.png)
### Mondel – ANN
* Accuracy : 0.97 
* D-P
* J-T
* J-X

![](https://user-images.githubusercontent.com/43957213/126810379-f5b981a3-3ee9-4850-b3bc-4ba770879a2c.png)
## Conclusion
* Only need 28 features for each data
* Accuracy is high
* D-P is hard to identify
* Not very general
* Highly depends on user


