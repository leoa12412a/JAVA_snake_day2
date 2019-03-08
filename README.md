## JAVA_snake_day2

# 同個package互相傳遞

  當我們程式出現new得時候，程式會跟記憶體申請記憶體空間，而static變數就是在載入程式後會主動配給記憶體給程式(僅一次)，後續無論實例化多少次，記憶體位置都一樣。所以我們不同的function只有抓取同一個記憶體位置就可抓到同樣的資料。
  
# JavaTimer
  
  首先我們需要自行撰寫一個繼承了 TimerTask 的 class，其中必須覆寫 run()，並在裡面填上我們要執行的工作
  
  ```
  1 package werdna1222coldcodes.blogspot.com.demo.timer;
  2 
  3 import java.util.*;
  4 
  5 public class DateTask extends TimerTask {
  6     
  7     @ Override
  8     public void run() {
  9         System.out.println("Task 執行時間：" + new Date());
 10     }
 11 }
  ```
