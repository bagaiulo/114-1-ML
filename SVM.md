# 114-1-ML SVM訓練過程

# 核心邏輯: <br>
找到一個決策邊(decisiion boundary)讓兩類之間的邊界(margins)最大化，使其可以完美區分開來<br>

<img width="630" height="353" alt="image" src="https://github.com/user-attachments/assets/1feec67e-3876-4b5c-88d7-f4eb2041d3b8" /> <br>
## 1.Linear SVM <br>
假設訓練資料為  
<img width="511" height="83" alt="image" src="https://github.com/user-attachments/assets/28531b69-f57b-494c-8b67-5c02f7c9c107" />    
<img width="406" height="126" alt="image" src="https://github.com/user-attachments/assets/8e39d76e-e08a-48b7-8803-e7e7de568fb9" />  

不考慮資料混在一起的情況下，也是所有資料都可以被完美分類(hard-margin SVM)  
<img width="723" height="119" alt="image" src="https://github.com/user-attachments/assets/03237783-1516-4421-b94e-149cd73f3a21" />  
所以SVM在找Optimal hyperplane就是希望區隔兩類之間的邊界(2/|w|)可以越大越好。轉換成數學公式如下  
<img width="434" height="117" alt="image" src="https://github.com/user-attachments/assets/c836256a-13c2-4684-8536-4ea31759f68a" />

