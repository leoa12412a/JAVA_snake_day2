## JAVA_snake_day2

# 同個package互相傳遞

  當我們程式出現new得時候，程式會跟記憶體申請記憶體空間，而static變數就是在載入程式後會主動配給記憶體給程式(僅一次)，後續無論實例化多少次，記憶體位置都一樣。所以我們不同的function只有抓取同一個記憶體位置就可抓到同樣的資料。
  
# JavaTimer
  
  首先我們需要自行撰寫一個繼承了 TimerTask 的 class，其中必須覆寫 run()，並在裡面填上我們要執行的工作，而下圖的工作就是印出 "現在時間："+現在的時間
  
  ```
  1 package werdna1222coldcodes.blogspot.com.demo.timer;
  2 
  3 import java.util.*;
  4 
  5 public class DateTask extends TimerTask {
  6     
  7     @ Override
  8     public void run() {
  9         System.out.println("現在時間：" + new Date());
 10     }
 11 }
  ```
  接下來是建立一個Timer來設定排成，建立的方法如下
  
  ```
  Timer timer = new Timer
  ```
  設定排程有幾種方法
  
  timer.schedule後面加上(task,delay,period)，就會在延遲dalay秒後，執行task，接下來每間格period執行一次task，根據後面的參數會有不同的排程方式
  
  如下圖，delay100(千分之一秒)後，執行task，只會執行一次
  ```
   timer.schedule(task, 100);
  ```
  
  如下圖，delay100(千分之一秒)後，執行task，每間格3秒執行一次task
  ```
   timer.schedule(task, 100,3000);
  ```
  
  如下圖，在準確時間(firstTime)，執行一次，接下來每間格5秒執行一次task
  ```
   Calendar calendar = Calendar.getInstance();
   calendar.set(Calendar.SECOND, calendar.get(Calendar.SECOND)+15);
   Date firstTime = calendar.getTime();
   
   timer.schedule(task , firstTime , 5000);
   
  ```
