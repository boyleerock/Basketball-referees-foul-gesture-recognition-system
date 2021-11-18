# Basketball-referees-foul-gesture-recognition-system

### Result:

Boxing the referee with a foul label and its predicted percentage:

<img width="247" alt="holding foul" src="https://user-images.githubusercontent.com/61671531/142389043-f67e4d7b-b0fe-4b87-b5f6-f4308ea43e0b.png">

### Demo Video:

https://user-images.githubusercontent.com/61671531/142387758-af1524db-c6f7-4995-a17f-3f64c57d59a0.mp4

Demo Videos for each foul on Youtube>>>[CLICK HERE](https://www.youtube.com/playlist?list=PLsQ9Nh7BGa-iEB3qGLAQrYaBvTKtaPmK-)

### Abstract:
有鑑於現今籃球比賽犯規紀錄繁雜，紀錄台人員需耗費大量心力在比對裁判的判決，為避免人為判斷的疏失，故本系統使用AI 影像辨識來追蹤裁判及學習裁判犯規的手勢，期許此系統可以幫助紀錄台人員的工作，降低人力成本，增加比賽進行的效率。
 
我將實際的籃球比賽影片作為資料，以**YOLOv5**追蹤裁判位置，再針對籃球常見的四種犯規(**阻擋、推人、拉手、進攻犯規**)以**mediapipe**擷取身體結點，透過**KNN model** trainnig，最後結合完成裁判追蹤及犯規手勢辨識的系統。


### Methods:

<img width="568" alt="system slow" src="https://user-images.githubusercontent.com/61671531/142393084-d534bf28-fce2-4c32-820d-7f7015bcf9d9.png">

#### 1. 追蹤裁判系統:
1.1. 蒐集資料: 從youtube上抓取影片，並使用PowerPoint 和 PicPick擷取連續動作的圖片。
2.2. 前處理資料: 使用Labelimg 抓取各別裁判人員的特徵(ex: 裁判服裝)，以得到Label座標值txt檔。
2.3. 並使用YOLOv4(可以商業化), YOLOv5(減少訓練時間80%) 訓練處理後的資料，以成功追蹤裁判的位置

#### 2. 犯規手勢辨識系統:
2.1. 蒐集資料: 從youtube上抓取影片，並使用PowerPoint 和 PotPlayer擷取連續動作的圖片。
2.2. 前處理資料: 使用Labelimg 抓取各別裁判手勢特徵(ex: 球員號碼、犯規種類)，以得到Label座標值txt檔(圖)。
2.3. 使用YOLOv4(優點: 可以商業化), YOLOv5(優點: 減少訓練時間80%) 訓練處理後的資料，以成功辨識裁判犯規手勢的結果(圖)。
