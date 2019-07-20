# App_reviews_crawler
icook_reviews_crawler

在嘗試爬取google應用商店的評論時發現了一個特別的方法


連結到想要爬取的app點擊所有評論後，直接在google chrome的console輸入以下指令(需要下滑網頁將所以評論導出，不然只能爬取當前頁面評論)

![GitHub](https://github.com/chiajung0001/App_reviews_crawler/blob/master/chrome_console.png)

```
var reviews = document.querySelectorAll('div[class="d15Mdf bAhLNe"]')
	
  var data = []
  reviews.forEach(v => data.push({body: v.outerHTML}))
```



接著輸入
```
copy(data)
```
將評論資料複製到剪貼簿，接著只需要在任意文字編輯軟體上貼上數據即可

所爬取內容包含用戶名稱、星級和評論

接著可以用python對json文本進行預處理(將josn轉為csv)

整理過後的資料如以下所示

![Github](https://github.com/chiajung0001/App_reviews_crawler/blob/master/reviews_df.png)



5星評論文字雲

![Github](https://github.com/chiajung0001/App_reviews_crawler/blob/master/wordcloud_5.png)

雖然示五星評論但大部分都是在抱怨訂閱價格

（<br>）

1~2星評論文字雲

![Github](https://github.com/chiajung0001/App_reviews_crawler/blob/master/wordcloud_2.png)

負評大部分跟系統更新與註冊問題有關


