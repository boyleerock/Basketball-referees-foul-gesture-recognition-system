# Basketball-referees-foul-gesture-recognition-system

### Result:

Boxing the referee with a foul label and its predicted percentage:

<img width="247" alt="holding foul" src="https://user-images.githubusercontent.com/61671531/142389043-f67e4d7b-b0fe-4b87-b5f6-f4308ea43e0b.png">

### Demo Video:

https://user-images.githubusercontent.com/61671531/142387758-af1524db-c6f7-4995-a17f-3f64c57d59a0.mp4

Demo Videos for each foul on Youtube>>>[CLICK HERE](https://www.youtube.com/playlist?list=PLsQ9Nh7BGa-iEB3qGLAQrYaBvTKtaPmK-)

### Abstract:
有鑑於現今籃球比賽犯規紀錄繁雜，紀錄台人員需耗費大量心力在比對裁判的判決，為避免人為判斷的疏失，所以本系統使用AI 影像辨識來追蹤裁判及學習裁判犯規的手勢，可望取代紀錄台人員，降低人力成本，增加比賽進行的效率。
 
我將實際的籃球比賽影片作為資料，以YOLOv5追蹤裁判位置，再針對籃球常見的四種犯規(阻擋、推人、拉手、進攻犯規)以mediapipe擷取身體結點，透過KNN model trainnig，最後結合完成裁判追蹤及犯規手勢辨識的系統。


### Methods:
