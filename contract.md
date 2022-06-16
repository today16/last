|合約1:|clickSignin()|
|-|-|
|操作:|clickSignin()|
|交互參照:|登入作業|
|前置條件:|已註冊帳號|
|後置條件:|-跟資料庫驗證帳號verifyAccount()<br>-回報登入結果returnLoginResult()|

|合約2:|verifyAccount()|
|-|-|
|操作:|verifyAccount()|
|交互參照:|登入作業|
|前置條件:|已註冊帳號|
|後置條件:|-回報登入結果returnLoginResult()|

|合約3:|FillInTheBasicInformation()|
|-|-|
|操作:|FillInTheBasicInformation()|
|交互參照:|填寫基本資料作業|
|前置條件:|已經登入成功|
|後置條件:|-傳送給資料庫passToDatabase(name,home,number)|

|合約4:|passToDatabase()|
|-|-|
|操作:|passToDatabase(name,home,number)|
|交互參照:|填寫基本資料作業|
|前置條件:|已經登入成功|
|後置條件:|-回報註冊結果reportAccessComplete()|

|合約5:|addMealToCart()|
|-|-|
|操作:|addMealToCart()|
|交互參照:|下訂單作業|
|前置條件:|已經登入成功|
|後置條件:|-顯示購物車內容showCartContents(Order)<br>-結帳payMoney()|

|合約6:|payMoney()|
|-|-|
|操作:|payMoney()|
|交互參照:|下訂單作業|
|前置條件:|已經送出訂單|
|後置條件:|-傳送給資料庫sendToDatabase()<br>-回傳結果reportAccessComplete()|

|合約7:|checkingOrder()|
|-|-|
|操作:|checkingOrder()|
|交互參照:|查詢訂單作業|
|前置條件:|已經下訂單了|
|後置條件:|-傳送歷史訂單內容sendHistoricalOrderContent()|

|合約8:|payToTheCreditCardCompany()|
|-|-|
|操作:|payToTheCreditCardCompany()|
|交互參照:|付款作業|
|前置條件:|完成訂單了|
|後置條件:|-回報付款結果reportPaymentResult()|

|合約9:|askForRefund()|
|-|-|
|操作:|askForRefund()|
|交互參照:|退款作業|
|前置條件:|訂單有問題|
|後置條件:|-回報退款結果Refund()|

|合約10:|reportProblem()|
|-|-|
|操作:|reportProblem()|
|交互參照:|聯絡客服作業|
|前置條件:|訂單有問題|
|後置條件:|-客服中心要回復客人replyToTheGuest()|

|合約11:|logoutOfTheSystem()|
|-|-|
|操作:|logoutOfTheSystem()|
|交互參照:|登出作業|
|前置條件:|離開網頁|
|後置條件:|-跳出登出訊息showLoggedOutMessage()|

|合約12:|checkWalletBalance()|
|-|-|
|操作:|checkWalletBalance()|
|交互參照:|事前作業|
|前置條件:|登入外送app|
|後置條件:|-從資料庫查詢錢包餘額再回傳介面showWalletBalance()|

|合約13:|scheduleWorkHours()|
|-|-|
|操作:|scheduleWorkHours()|
|交互參照:|事前作業|
|前置條件:|登入外送app|
|後置條件:|-把此動作記錄在資料庫recordWorkingHours()<br>-顯示排班結果showShiftSuccess()|

|合約14:|acceptOrder()|
|-|-|
|操作:|acceptOrder()|
|交互參照:|接單作業|
|前置條件:|登入外送app|
|後置條件:|-前往配送訂單goToDelivery()<br>-回報配送結果reportDelivered()|

|合約15:|receptionProblem()|
|-|-|
|操作:|receptionProblem()|
|交互參照:|客服解決問題作業|
|前置條件:|登入系統|
|後置條件:|-解決客人問題problemSolved()|

|合約16:|checkSystem()|
|-|-|
|操作:|checkSystem()|
|交互參照:|維護網站作業|
|前置條件:|登入後台|
|後置條件:|-定時檢查網頁與後台checkWeb()|