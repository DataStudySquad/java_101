# Java Turtorial pt.2

這份擴展指南將專注於 Java 的**語法細節（Syntax）**、**內建基本功能（Basic Functions）**，以及最重要的：**如何定義與使用自定義函數（Methods/Functions）**。

---

# 🛠️ Java 深度語法與函數指南 (20 分鐘精華)

## 1. 語法細節：那些「必須遵守」的小規則

在 Java 裡，電腦非常挑剔。如果漏掉一個符號，程式就不會跑。

* **分號 (`;`)**：每一句指令的結尾都要加分號，就像寫文章的句號。
* **大括號 (`{ }`)**：用來定義「一個範圍」。例如一個 Class 的範圍，或一個 If 判斷式的範圍。
* **大小寫區分**：`myname` 和 `myName` 在 Java 眼中是完全不同的兩個人。
* **註解**：
* `//` 單行註解（給人看的筆記）。
* `/* ... */` 多行註解。



---

## 2. 核心內建功能 (Basic Functions)

Java 內建了很多「工具箱」，你不需要自己發明輪子。

### 數學運算 (Math Class)

```java
double root = Math.sqrt(16);   // 開根號，結果是 4.0
double power = Math.pow(2, 3); // 2 的 3 次方，結果是 8.0
int maxNum = Math.max(10, 20); // 找出較大的數，結果是 20
double random = Math.random(); // 產生 0 到 1 之間的隨機小數

```

### 字串處理 (String Functions)

```java
String text = "Hello Java";
int len = text.length();        // 算長度：10
char letter = text.charAt(0);   // 抓第一個字：'H'
String upper = text.toUpperCase(); // 轉大寫："HELLO JAVA"
boolean hasJava = text.contains("Java"); // 檢查是否包含某字：true

```

---

## 3. 函數 (Method/Function)：你的專屬工具 (重點！)

當你的程式碼變長時，你會發現有些動作一直在重複（例如：計算稅金）。這時我們就把這段動作包裝成一個「**函數 (Method)**」。

### 函數的構造解剖圖

一個標準的函數長這樣：

```java
public static 回傳類型 函數名稱 (參數類型 參數名稱) {
    // 執行的內容
    return 回傳值;
}

```

### 實作演練：建立一個「自動打招呼」機器人

```java
public class Main {
    // 這是主程式入口
    public static void main(String[] args) {
        // 呼叫我們寫好的函數
        sayHi("小明"); 
        
        int myTotal = add(5, 10); // 呼叫加法函數，並把結果存在變數裡
        System.out.println("加法結果是：" + myTotal);
    }

    // --- 以下是自定義函數 ---

    // 1. 沒有回傳值的函數 (使用 void)
    public static void sayHi(String name) {
        System.out.println("你好，" + name + "！歡迎來到 Java 世界。");
    }

    // 2. 有回傳值的函數 (回傳整數 int)
    public static int add(int num1, int num2) {
        int result = num1 + num2;
        return result; // 把算好的結果「丟回去」給呼叫的人
    }
}

```

---

## 4. 為什麼要用函數？(設計思維)

想像你在寫一個購物網站：

1. **不使用函數**：每次結帳都要寫 10 行程式碼算運費。如果有 10 個地方要結帳，你要寫 100 行。如果要改運費規則，你要改 10 個地方（超累且容易出錯）。
2. **使用函數**：寫一個 `calculateShipping()` 函數。所有地方都直接呼叫它。改規則時，只要改這一個函數，全世界都跟著改好了。

---

## 5. 變數的範圍 (Scope)

這是一個新手常犯的錯誤：

* **區域變數**：在函數內定義的變數，外面的人看不到。
* **比喻**：你在家裡客廳（函數 A）放的手機，你在臥室（函數 B）是找不到的。

```java
public static void test() {
    int secret = 100;
}

public static void main(String[] args) {
    // System.out.println(secret); // 這會報錯！因為 main 看不到 test 裡的 secret
}

```

---

## 💡 本節小結

1. **語法**：分號不能漏，括號要對稱。
2. **內建功能**：善用 `Math` 和 `String` 工具。
3. **函數**：
* `void` = 執行完就結束，不拿回東西。
* `int`, `String` 等 = 執行完會 `return` 一個結果給你。
