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
##hard-margin SVM跟soft-margin SVM  
hard-margin SVM(硬邊界):通常資料在特徵空間中 完全可線性分，讓兩類到決策面的間距（margin）最大。  
<img width="322" height="46" alt="image" src="https://github.com/user-attachments/assets/364190df-3afc-45c3-a288-a2beefee3721" />  
特性：不允許任何點在邊界內或被分錯；對離群點極度敏感  
soft-margin SVM (軟邊界):現實資料多半不能完美線性分，會有噪聲/重疊。因此允許每個樣本有一點「違規量」，<img width="62" height="37" alt="image" src="https://github.com/user-attachments/assets/e739c909-9731-410c-871a-f580882d5d73" />  同時用超參數 C 懲罰這些違規。  
<img width="536" height="68" alt="image" src="https://github.com/user-attachments/assets/8eccb6ec-bcb9-4862-8261-00c33327db0b" />  
等價於「最大間距 + 最小錯誤」的權衡，更抗噪、可適應少量錯分；是實務上的預設。
也因此大多數訓練過程都選用軟邊界對超過的範圍做逞罰。  


## 2.Soft-margin SVM（允許誤差/離群點)
加入鬆弛變數與懲罰係數  
<img width="406" height="101" alt="image" src="https://github.com/user-attachments/assets/0b7c36e5-facc-4bac-af61-5d37f1293798" />  
PS:  
<img width="641" height="53" alt="image" src="https://github.com/user-attachments/assets/796b3147-71b6-4406-9c1d-a6c7105bc664" />


 
	​

