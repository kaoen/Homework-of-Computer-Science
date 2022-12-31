# Homework_of_Computer_Science

## Week2
---

### Linux 命名規則

* 區分英文字元的大小寫，以小寫為主
* 長度至多 256 個字元，可包括字母、數字、"."(點)、"_"(下劃線)和"-"(連字元)
* 不可使用的字元："?"(問號),"*"(星號), " "(空格), "$"(貨幣符), "&", "("括號, "/" (斜線), ".."
* 前面有"."(點)，為隱藏檔 e.g. .filename

### Linux 指令

| 指令 | 功能、用途 |
| :--- | :--- |
| ` cd ` | ` 變換目錄 ` |
| ` pwd ` | ` 顯示目前的目錄的所在位置 ` |
| ` ls ` | ` 顯示目錄下的所有檔案 ` |
| ` touch ` | ` 建立檔案 ` |
| cp | 複製 |
| cat | 查看檔案內容 |
| vi | 編輯檔案 |
| ` mkdir ` | ` 建立一個新目錄 ` |
| mkdir -p | 同時建立多個目錄 |
| rmdir | 刪除一個裡面是空的空目錄 |
| ` rm ` | ` 刪除檔案 ` |
| rm -r | 強制刪除 |
| mv | 移動、重新命名 |

### Linux 指令 —— 絕對路徑 && 相對路徑

* 絕對路徑：由根目錄寫起
* 相對路徑：相對於目前工作目錄的路徑
* 特殊目錄
  * 「.」：此層目錄
  * 「..」：上一層目錄
  * 「-」：前一個工作目錄
  * 「~」：「目前使用者身分」的家目錄

### Linux 指令 —— 查看檔案目錄資訊

* ls -l：顯示目錄下的所有檔案詳細資訊
* ls -al：顯示目錄下的所有檔案（包含隱藏檔）詳細資訊

### Linux 指令 —— 更改檔案或目錄權限

* chown：修改檔案或目錄的擁有者及群組

### Linux 指令 —— 更改使用者權限

![image](https://user-images.githubusercontent.com/112980770/210140304-109a93fd-25c3-45d6-b397-6c4db9dd0048.png)

### Linux 指令 —— 目錄權限

![image](https://user-images.githubusercontent.com/112980770/210140333-9dd611a4-ffa6-495e-97ff-2cb9befae0e2.png)

## Week3
---

### Linux 背景知識 —— 選擇何種壓縮方式（考慮的因素）

* 壓縮率（compression ratio），能夠將檔案壓到多小
* 解壓縮所需的時間，也就是需要的 CPU 計算量
* 解壓縮所需的記憶體空間
* 相容性（compatibility），即解壓縮程式的普遍性，是不是大部分人都有辦法解壓縮這種格式？

### Linux 背景知識 —— 選擇何種壓縮方式（總結）

* 需要在記憶體很小的機器（如小於 128MB）上解壓縮時，則選擇 gzip 格式
* 需要在很簡單、沒有什麼工具可用的機器解壓縮時，則選擇 gzip 格式
* 需要節省網路頻寬、縮短下載所需要的時間時，則選擇 xz 格式
* 需要有最好的壓縮率時，則選擇tar.xz 格式

### Linux 指令 —— 壓縮檔案

* gzip
   * 壓縮：gzip filename
   * 解壓縮：
       1. gunzip filename.gz
       2. gzip -d filename.gz
* xz
   * 壓縮：xz -z filename
   * 解壓縮：xz -d filename.xz
* tar.gz
   * 壓縮：tar -zcvf FileName.tar.gz DirName
   * 解壓縮：tar -zxvf FileName.tar.gz9

### Linux 指令 —— 檔案 && 文字相關

* echo
    * 基礎
        * 用法：echo "text"
        * 效果：印出文字
    * 進階
        * 用法：echo "text" >> filename （接續在原檔案內容後）|| echo "text" > filename （覆蓋原檔案內容）
        * 效果：將文字寫入>> || > 後的檔案
* cat （concatenate）
    * 效果：將文件內容串接後顯示
    * 用法：cat file1 file2

### Q && A

Q：檔案為什麼沒有副檔名
A：Linux不依靠副檔名來判斷檔案類型

### Linux背景知識 —— 資料傳輸

![image](https://user-images.githubusercontent.com/112980770/210152551-5d6ba914-9f03-4f55-8d5a-2ed4f5a114c4.png)

* Port
> 通訊埠號是 TCP/UDP 與上層通訊的通道，當 TCP/UDP 要傳送訊息時，會指定要由哪一個通訊埠號來接收。一些常用的服務會使用特定的埠號來等待要求的訊息。埠號是由 16 個位元所組成的號碼，0 ~ 255 為保留號碼，256 ~ 65535 則可自行設定。
* TCP/IP
> TCP/IP提供了點對點的連結機制，將資料應該如何封裝、定址、傳輸、路由以及在目的地如何接收，都加以標準化。它將軟體通信過程抽象化為四個抽象層，採取協議堆疊的方式，分別實作出不同通信協定。協定套組下的各種協議，依其功能不同，被分別歸屬到這四個階層之中，常被視為是簡化的七層OSI模型。
