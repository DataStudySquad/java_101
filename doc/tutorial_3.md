# Java Turtorial pt.3


這是一個非常經典且適合新手的微型專案：**「簡易 BMI 健康計算器」**。

這個專案會運用到你剛才學到的所有觀念：**變數、輸入/輸出、數學運算、If 判斷**，以及**自定義函數**。

---

## 🏆 挑戰目標：BMI 計算機

我們要把這台機器拆解成兩個部分：

1. **邏輯大腦 (Function)**：負責計算數字並回傳等級。
2. **互動窗口 (Main)**：負責問使用者問題，並顯示結果。

### 📋 完整程式碼範例

你可以將以下程式碼複製到 [Online Java Compiler](https://www.programiz.com/java-programming/online-compiler/) 執行：

```java
import java.util.Scanner; // 1. 導入掃描器工具

public class BMICalculator {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("=== Java 健康計算機 ===");
        
        // 2. 獲取使用者輸入
        System.out.print("請輸入體重 (kg): ");
        double weight = sc.nextDouble();
        
        System.out.print("請輸入身高 (cm): ");
        double heightCm = sc.nextDouble();

        // 3. 呼叫我們自定義的函數來計算 BMI
        double bmi = calculateBMI(weight, heightCm);
        
        // 4. 顯示結果 (使用 printf 可以限制小數點位數，%.2f 代表顯示到小數後兩位)
        System.out.printf("您的 BMI 值為: %.2f \n", bmi);
        
        // 5. 呼叫判斷等級的函數
        String result = getBMICategory(bmi);
        System.out.println("健康診斷: " + result);
        
        System.out.println("======================");
    }

    // --- 自定義函數區 ---

    /**
     * 計算 BMI 的函數
     * 公式: 體重(kg) / [身高(m) * 身高(m)]
     */
    public static double calculateBMI(double w, double hCm) {
        double hMeter = hCm / 100; // 先把公分換算成公尺
        return w / (hMeter * hMeter);
    }

    /**
     * 判斷 BMI 等級的函數
     */
    public static String getBMICategory(double bmi) {
        if (bmi < 18.5) {
            return "體重過輕 (多吃一點！)";
        } else if (bmi >= 18.5 && bmi < 24) {
            return "正常範圍 (太棒了，繼續保持！)";
        } else if (bmi >= 24 && bmi < 27) {
            return "過重 (要注意飲食囉)";
        } else {
            return "肥胖 (該運動了喔！)";
        }
    }
}

```

---

## 🔍 重點解析 (解說給沒背景的你)

### 1. `double` 的重要性

為什麼體重和身高不用 `int`？因為身高體重通常有小數點（例如 65.5 kg），且 BMI 計算結果也是精確的小數，所以我們統一使用 `double`。

### 2. 函數的解耦 (Decoupling)

你會發現我們把「計算」(`calculateBMI`) 和「判斷」(`getBMICategory`) 分開寫成兩個函數。

* **優點**：如果以後你想把這台機器改裝成「手機 App」或「網頁版」，這兩個計算邏輯可以直接搬過去，不需要重新修改。

### 3. `System.out.printf`

這是一個進階的輸出語法。因為 BMI 算出來可能是 `22.857142...` 這一長串，`%.2f` 能幫我們優雅地只顯示到小數點後兩位。

---

## 🚀 你的下一個微型挑戰 (進階練習)

如果你覺得上面的 BMI 計算機太簡單了，可以試著修改程式碼加入以下功能：

1. **加入 While 迴圈**：讓程式執行完一次後，問使用者「是否繼續計算？(Y/N)」，而不是直接結束。
2. **單位換算**：增加一個函數，讓使用者可以選擇輸入「英制單位 (磅/英吋)」，程式會自動換算成公制再計算 BMI。



