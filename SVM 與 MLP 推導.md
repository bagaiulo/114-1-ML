# 114-1-ML SVM推導

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
## 2.hard-margin SVM跟soft-margin SVM  
hard-margin SVM(硬邊界):通常資料在特徵空間中 完全可線性分，讓兩類到決策面的間距（margin）最大。  
<img width="322" height="46" alt="image" src="https://github.com/user-attachments/assets/364190df-3afc-45c3-a288-a2beefee3721" />  
特性：不允許任何點在邊界內或被分錯；對離群點極度敏感  
soft-margin SVM (軟邊界):現實資料多半不能完美線性分，會有噪聲/重疊。因此允許每個樣本有一點「違規量」，<img width="62" height="37" alt="image" src="https://github.com/user-attachments/assets/e739c909-9731-410c-871a-f580882d5d73" />  同時用超參數 C 懲罰這些違規。  
<img width="536" height="68" alt="image" src="https://github.com/user-attachments/assets/8eccb6ec-bcb9-4862-8261-00c33327db0b" />  
等價於「最大間距 + 最小錯誤」的權衡，更抗噪、可適應少量錯分；是實務上的預設。
也因此大多數訓練過程都選用軟邊界對超過的範圍做逞罰。  


## 3.Soft-margin SVM（允許誤差/離群點)
加入鬆弛變數與懲罰係數  
<img width="406" height="101" alt="image" src="https://github.com/user-attachments/assets/0b7c36e5-facc-4bac-af61-5d37f1293798" />  
PS:  
<img width="641" height="53" alt="image" src="https://github.com/user-attachments/assets/796b3147-71b6-4406-9c1d-a6c7105bc664" />

因為未知參數在限制式內，無法直接去解此最佳化問題，因此在解「 有條件的最佳化問題」時，有時需要把原本的問題轉換成對偶問題(Dual Problem)後，會比較好解。  
用Lagrangian dual function (因為有兩種限制式所以Lagrangian parameters為αi>=0和βi>=0)將原最佳化問題轉換成Lagrangian函式:  
<img width="726" height="102" alt="image" src="https://github.com/user-attachments/assets/46f41db3-b72b-4979-92d9-1b2418d7eea5" />  
如果我們要得到參數的最佳解，則直接將Lagrangian函式偏微分該參數  
<img width="543" height="271" alt="image" src="https://github.com/user-attachments/assets/e6ba4180-c09f-4c09-a2ef-5c6ee27c4a52" />  
我們將最佳化問題做個轉換  
<img width="375" height="290" alt="image" src="https://github.com/user-attachments/assets/47f41419-39f5-4670-9a38-ed2ca8a3236e" />  
二次式(Quadratic Programming)的精神是要將函數呈現成下式:  
<img width="273" height="149" alt="image" src="https://github.com/user-attachments/assets/c05a0fbb-4fcc-4fad-bf1e-df74fa06ceb9" />
​H是Hessian matrix，為對稱矩陣  

根據不同的參數特性，可以得到對問題不同的結論  

· 如果H是半正定矩陣，那麼f(x)是一個凸函數。  

· 如果H是正定矩陣，那麼全局最小值就是唯一的。  

· 如果H=0，二次規劃問題就變成線性規劃問題。  

如果有至少一個向量x滿足約束而且f(x)在可行域有下界，二次規劃問題就有一個全局最小值x。  

所以SVM最後其實只是一個二次式求解問題，整理後如下列方程式:  
<img width="715" height="408" alt="image" src="https://github.com/user-attachments/assets/914b2d57-2846-423d-960a-a815f5423ac4" />

# MLP推導 
## 1.機器學習- 神經網路(多層感知機 Multilayer perceptron, MLP)  
多層感知機是一種前向傳遞類神經網路，至少包含三層結構(輸入層、隱藏層和輸出層)，並且利用到「倒傳遞」的技術達到學習(model learning)的監督式學習，以上是傳統的定義。現在深度學習的發展，其實MLP是深度神經網路(deep neural network, DNN)的一種special case，概念基本上一樣  
<img width="664" height="442" alt="image" src="https://github.com/user-attachments/assets/965be09d-f6ca-4ce2-91bb-96edc2290c54" />  
假設有個MLP的結構，共有n筆樣本，每個樣本對應m個輸出值。隱藏層只有一層設定為p個hidden node  
<img width="503" height="84" alt="image" src="https://github.com/user-attachments/assets/f12aac68-1985-42ea-8b5b-6006d8c4a39b" />  
## 2.前向傳遞 (Forward propagation)  
輸入層到隱藏層  
<img width="694" height="293" alt="image" src="https://github.com/user-attachments/assets/e888dc8a-7915-44ab-a721-73b03cd34bb6" />  
輸入層到隱藏層的值為sk,k=1,…,p，為輸入訊號的加權線性和(vik為第i個輸入到第k個hidden node的權重)  
<img width="181" height="115" alt="image" src="https://github.com/user-attachments/assets/712aea50-3c5a-47c5-b241-9cbd0956a846" />  
經過 非線性轉換/激活函數(activation function，f1)後，得到hidden node的輸出hk  
<img width="195" height="70" alt="image" src="https://github.com/user-attachments/assets/c09338b7-a3d8-48c2-b4c8-397bc83a9971" />  
隱藏層到輸出層  
<img width="718" height="304" alt="image" src="https://github.com/user-attachments/assets/1cc563eb-11d4-43e5-886d-7f53c8cc4379" />  
隱藏層到輸出層的值為zj,j=1,…,m，為hidden node輸出的加權線性和(wkj為第k個hidden node輸出到第j個輸出值的權重  
<img width="408" height="198" alt="image" src="https://github.com/user-attachments/assets/d251dc13-6291-4421-8f80-d6cf7c5ee566" />  
經過 非線性轉換/激活函數(activation function，f2)後，得到推估的輸出值y^j  


