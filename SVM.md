# 114-1-ML SVM訓練過程

# 核心邏輯: <br>
找到一個決策邊(decisiion boundary)讓兩類之間的邊界(margins)最大化，使其可以完美區分開來<br>

<img width="630" height="353" alt="image" src="https://github.com/user-attachments/assets/1feec67e-3876-4b5c-88d7-f4eb2041d3b8" /> <br>
## 1.Linear SVM <br>
將中間斜線設為ax+by+c=0 轉換成矩陣表示<br>
<img width="371" height="162" alt="image" src="https://github.com/user-attachments/assets/66c7e3db-9e39-4a85-adb6-a5169d87d69b" /> <br>
求出點到最近圈圈線條的最短距離即是margin，對兩邊拉出一條邊界線假設是<br>



利用最小化法求出<br>
<img width="504" height="116" alt="image" src="https://github.com/user-attachments/assets/f64c7d3d-a52f-49e4-9ac8-a57d37d6db32" /><br>


