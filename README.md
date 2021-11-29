# Basketball-referees-foul-gesture-recognition-system
# 籃球裁判追蹤及犯規手勢辨識系統
### Abstract:
有鑑於現今籃球比賽犯規紀錄繁雜，紀錄台人員需耗費大量心力在比對裁判的判決，為避免人為判斷的疏失，故本系統使用AI 影像辨識來追蹤裁判及學習裁判犯規的手勢，期許此系統可以幫助紀錄台人員的工作，降低人力成本，增加比賽進行的效率。
 
我將實際的籃球比賽影片作為資料，以**YOLOv5**追蹤裁判位置，再針對籃球常見的四種犯規(**阻擋、推人、拉手、進攻犯規**)以**mediapipe**擷取身體結點，透過**KNN model** trainnig，最後結合完成裁判追蹤及犯規手勢辨識的系統。


### Result:

Boxing the referee with a foul label and its predicted percentage:

<img width="247" alt="holding foul" src="https://user-images.githubusercontent.com/61671531/142389043-f67e4d7b-b0fe-4b87-b5f6-f4308ea43e0b.png">

### Demo Video:

https://user-images.githubusercontent.com/61671531/142387758-af1524db-c6f7-4995-a17f-3f64c57d59a0.mp4

Demo Videos for each foul on Youtube>>>[CLICK HERE](https://www.youtube.com/playlist?list=PLsQ9Nh7BGa-iEB3qGLAQrYaBvTKtaPmK-)

### Methods:
<img width="395" alt="Screenshot 2021-11-29 120626" src="https://user-images.githubusercontent.com/61671531/143807253-bb346825-18ab-4fc8-b4ff-15e4a968e143.png">

<img width="568" alt="system slow" src="https://user-images.githubusercontent.com/61671531/142393084-d534bf28-fce2-4c32-820d-7f7015bcf9d9.png">

#### 1. 追蹤裁判:
1.1. 蒐集資料: 從youtube上抓取影片，並使用PowerPoint 和 PicPick擷取連續動作的圖片。 
<img width="407" alt="Screenshot 2021-11-29 120859" src="https://user-images.githubusercontent.com/61671531/143807519-522278f6-71b3-4057-9fe9-b0b45a29e556.png">

2.2. 前處理資料: 使用Labelimg 抓取各別裁判人員的特徵(ex: 裁判服裝)，以得到Label座標值txt檔。          
2.3. 並使用YOLOv4(可以商業化), YOLOv5(減少訓練時間80%) 訓練處理後的資料，以成功追蹤裁判的位置     

#### 2. 犯規手勢辨識:
2.1. 蒐集資料: 從youtube上抓取影片，並使用PowerPoint 和 PotPlayer擷取連續動作的圖片。
<img width="404" alt="Screenshot 2021-11-29 121030" src="https://user-images.githubusercontent.com/61671531/143807678-71f9ded4-2117-476d-b057-f4984cb89cd5.png">

2.2. 資料前處理：標準化

<img width="431" alt="Screenshot 2021-11-29 121226" src="https://user-images.githubusercontent.com/61671531/143807765-cfb99cc0-90ab-4cd5-b493-4d07936cb203.png">
<img width="426" alt="Screenshot 2021-11-29 121305" src="https://user-images.githubusercontent.com/61671531/143807824-986a373a-dbfd-4fb2-afec-942f88b32a19.png">


2.3. 使用KNN Model 訓練處理後的圖片資料，以辨識裁判犯規手勢的結果。    
<img width="467" alt="Screenshot 2021-11-29 121350" src="https://user-images.githubusercontent.com/61671531/143807896-0611e872-280a-4418-b365-b7b84046fa44.png">　　　　

**（因為犯規動作通常都是一段連續動作，我們抓7個frame判斷皆為同一犯規動作時才顯示Label結果）
<img width="386" alt="Screenshot 2021-11-29 121633" src="https://user-images.githubusercontent.com/61671531/143808157-50a4d50c-05a3-44af-8f2a-02d71754e048.png">　　　　　





