# CS_NOTE
## 路徑移動  
* 路徑  
  * 絕對路徑：由根目錄 / 寫起』，例如： /usr/share/doc 這個目錄。  
  * 相對路徑：不是由 / 寫起(相對於目前工作目錄的路徑)  
* 目錄指令  
  * cd 變換目錄    
  * pwd 顯示目前的目錄   
  * mkdir 建立一個新目錄   
  * ls 顯示目錄下的所有內容   
  * rmdir 刪除一個裡面是空的空目錄   
* 常用操作
  * cp 複製  
  * mv 移動   
  * cat 查看檔案內容  

## 目錄
* /.(根目錄) 所有的檔案的起始，只有root使用者具許可權
* /root  此目錄為系統管理員，也稱作超級許可權者的使用者主目錄
* /bin  儲存常用指令
* /boot  系統啟動必讀取的檔案，包括系統核心、連線檔案以及映象檔案
* /dev  存放周邊設備代號的檔案
* /etc  放置與系統設定、管理相關的檔案
* /home  存放普通使用者的主目錄，每個使用者都各自有以自己帳號命名的目錄
* /media  可用來做為光碟、軟碟片、隨身碟與其他分割區的自動掛載點
* /tmp  使用者暫時放置檔案的目錄
* /usr  非常重要的目錄,使用者大多應用程式和檔案都放在此目錄下
* /var  系統執行時,內容經常變動的資料或暫存檔 
   
## 使用者與群組  
* 身份分類：
  * user (owner)
  * group		
    * 將帳號歸類，有助於類似專案開發  
    * 每個使用者均可加入多個群組  
  * others			
  * root(系統管理員)
* 帳號分類:  
  * 系統帳號
  * 一般使用者帳號  
 
## 使用者權限
* 使用者
  * u：檔案擁有者
  * g：與該檔案的擁有者同一個群體者
  * o：其他以外的人
  * a：三者皆是
* 許可權
  * +  增加許可權
  * -  取消許可權
  * =  唯一設定許可權
* 方式
  * r：可讀取(4)
  * w：可寫入(2)
  * x：可執行(1)  

## 編輯文檔
* nano
  * Ctrl C：顯示游標所在
  * Ctrl W：查詢命令，按下後會跳轉到末行的反白位置
* vi/vim
  * 一般模式  
    * 可使用上下左右進行游標移動  
    * 刪除，複製，貼上字元和檔案     
  * 編輯模式  
    * i鍵進入編輯 
    * Esc鍵退出編輯
  * 命令列模式 _(！為『強制』的意思)_
    * :w 將資料寫入硬碟檔案中
    * :wq 儲存後離開
    * :wq! 強制儲存後離開 
    * :w! 若檔案屬性為『只讀』時，強制寫入檔案
    * :w[filename] 將編輯的資料儲存成另一個檔案（類似另存新檔）
    * :r[filename] 在資料中，讀入另一個檔案的資料
    * :set nu 顯示行號，設定後會在每一列的自首顯示該列的行號
    * :q 離開
    * :q! 強制離開不儲存檔案  
    
## 壓縮檔案
* 概念
  * 將重複的資料進行統計記錄
  * 使用bits單位計量,釋出閒置的空間
* 優點
  * 可以視情況進行加密
  * 方便整理、備份資料
  * 檔案變小節省電腦硬碟的空間
  * 將無數個散亂的檔案打包成一個較小的檔案，便於資訊在網路上流通  
* 考慮的因素
  * 壓縮率
  * 相容性
  * 解壓縮所需的時間
  * 解壓縮所需的記憶體空間
  
## 解壓縮類別
* gzip
  * 記憶體很小的機器
  * 很簡單、沒有什麼工具可用的機器
    * 壓縮  gzip FileName
    * 解壓縮一  gunzip FileName.gz 
    * 解壓縮二  gzip -d FileName.gz
* xz
  * 壓縮  xz -z FileName
  * 解壓縮  xz -d FileName.xz
* tar.gz
  * 壓縮  tar -zcvf FileName.tar.gz DirName
  * 解壓縮  tar -zxvf FileName.tar.gz
  
## 檔案搜索
* which filename
  * -n  指定文件名長度，指定的長度必須大於或等於所有文件中最長的文件名
  * -p  與-n参數相同，但此處多了文件的路徑
  * -w  指定輸出欄位的寬度
  * -V  顯示版本訊息
## 檔案內容查閱
* cat  從第一行顯示檔案內容、形成新檔案
  * -n  由1開始對所有輸出的行數編號
  * >  將多個文件覆蓋到目標文件中
  * >>  將多個文件追加到目標文件中
* tac  從最後一行開始顯示
  * -r  將分隔符作為基礎正規表達是處理
  * -s  使用String作為分隔符代替默認的換行符
* more 一頁一頁的顯示檔案內容
  * ENTER  向下n行(default為1行)
  * Ctrl+F/SPACE  向下滾動一屏
　* Ctrl+B  返回上一屏
* less 顯示檔案室允許用戶既可以向前又可以向後翻頁閱讀檔案
  * j  下一行
  * k  上一行
  * G  移動到最後一行
  * g  移動到第一行
* head/tail 只看頭/尾巴幾行
## 網路相關指令
* route
  * add  新增一條路由規則
  * del  刪除一條路由規則
  * -net  目的地址是一個網路
  * -host  目的地址是一個主機
  * target  目的網路或主機
  * netmask  目的地址的網路掩碼
  * gw  路由資料包通過的閘道器
  * dev  為路由指定的網路介面
