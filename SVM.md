# 114-1-ML SVM訓練過程

# 核心邏輯: <br>
找到一個決策邊(decisiion boundary)讓兩類之間的邊界(margins)最大化，使其可以完美區分開來<br>

<img width="630" height="353" alt="image" src="https://github.com/user-attachments/assets/1feec67e-3876-4b5c-88d7-f4eb2041d3b8" /> <br>
## 1.Linear SVM <br>
將中間斜線設為ax+by+c=0 轉換成矩陣表示<br>
<img width="371" height="162" alt="image" src="https://github.com/user-attachments/assets/66c7e3db-9e39-4a85-adb6-a5169d87d69b" /> <br>
求出點到最近圈圈線條的最短距離即是margin，對兩邊拉出一條邊界線假設是<br>
<img width="129" height="45" alt="image" src="https://github.com/user-attachments/assets/d046e6a0-c43a-4b5b-a789-b4d1df367f76" />     
<img width="133" height="44" alt="image" src="https://github.com/user-attachments/assets/47f201be-3209-4957-8c4e-665c650c1c89" />
