# Java Turtorial pt.1


## 💡 前言：程式碼的「語法糖」

對於初學者，Java 看起來有很多奇怪的單字（如 `public`, `static`, `void`）。**現在請先無視它們**。把它們當作啟動機器的「儀式」，我們把重點放在中間的「邏輯內容」。

---

## 第一階段：資料的容器 (0-5 分鐘)

想像你在整理家務，你需要不同尺寸的盒子來裝東西。在 Java 中，這叫 **宣告變數**。

### 1. 常用數據類型

* **`int`** (Integer): 整數（如：人數 `10`, 年齡 `25`）。
* **`double`**: 帶小數點的數字（如：體重 `65.5`, 價格 `99.99`）。
* **`String`**: 文字字串（如：`"Hello"`, `"王小明"`）。**注意：必須用雙引號**。
* **`boolean`**: 開關，只有兩種值：`true` (真) 或 `false` (假)。

### 實作範例

```java
String heroName = "鋼鐵俠";
int level = 50;
double hp = 450.5;
boolean isAlive = true;

System.out.println("角色：" + heroName + " | 等級：" + level);

```

---

## 第二階段：邏輯分叉路 - if 判斷 (5-10 分鐘)

程式如果不具備判斷力，就只是一台計算機。我們使用 `if...else` 來模擬現實世界的決策。

### 邏輯符號表

* `==`：等於（注意是兩個等號！）
* `!=`：不等於
* `>` / `<`：大於 / 小於
* `&&`：而且 (And)
* `||`：或者 (Or)

### 實作：模擬門禁系統

```java
int age = 17;
boolean hasTicket = true;

if (age >= 18 && hasTicket) {
    System.out.println("允許入場：您已成年且有票。");
} else if (age < 18 && hasTicket) {
    System.out.println("拒絕入場：雖然有票但未成年。");
} else {
    System.out.println("請去售票口買票。");
}

```

---

## 第三階段：自動化魔力 - 迴圈 (10-15 分鐘)

迴圈是程式最迷人的地方：它可以處理人類覺得無聊的重複工作。

### 1. For 迴圈 (計數)

當你知道要重複幾次時使用。

```java
// 從 1 數到 10
for (int i = 1; i <= 10; i++) {
    System.out.println("第 " + i + " 次深蹲");
}

```

### 2. While 迴圈 (條件)

當你不知道要跑幾次，直到某個條件達成時停止。

```java
int energy = 100;
while (energy > 0) {
    System.out.println("持續跑步中... 體力剩下：" + energy);
    energy -= 20; // 每次減 20
}
System.out.println("沒體力了，休息吧！");

```

---

## 第四階段：收納邏輯 - 方法 Method (15-20 分鐘)

如果你有一段邏輯會重複用到（例如：計算折扣價），你不必每次都重寫，而是把它包裝成一個「功能按鈕」。

### 實作：製作一個「計算機」

```java
public class Main {
    public static void main(String[] args) {
        // 呼叫我們寫好的按鈕
        checkDiscount(200); 
        checkDiscount(50);
    }

    // 這是一個自定義的「按鈕」 (Method)
    public static void checkDiscount(int price) {
        if (price >= 100) {
            System.out.println("特價中：" + (price * 0.8));
        } else {
            System.out.println("原價販售：" + price);
        }
    }
}

```

---
