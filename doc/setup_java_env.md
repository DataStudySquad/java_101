
# Java 開發環境設定指南

**作業系統:** Windows / macOS
**IDE:** IntelliJ IDEA 或 Visual Studio Code
**建議 Java 版本:** Java 17 或 Java 21 (LTS)

---

# 1. 安裝 Java (JDK)

開發 Java 程式需要 **Java Development Kit (JDK)**。

### 建議使用版本

**Eclipse Temurin (OpenJDK)**

### 下載方式

1. 前往網站
   [https://adoptium.net](https://adoptium.net)
2. 下載 **JDK 17 或 JDK 21**
3. 選擇你的作業系統（Windows / macOS）
4. 依照預設設定完成安裝

---

## 確認安裝成功

開啟 **Terminal / Command Prompt**

```bash
java -version
javac -version
```

範例輸出：

```
java version "21"
javac 21
```

---

# 2. 設定 JAVA_HOME

## Windows

1. 搜尋 **Environment Variables（環境變數）**
2. 點選 **Edit the system environment variables**
3. 點擊 **Environment Variables**

新增：

```
JAVA_HOME = C:\Program Files\Eclipse Adoptium\jdk-21
```

修改 `Path`，加入：

```
%JAVA_HOME%\bin
```

確認：

```bash
echo %JAVA_HOME%
```

---

## macOS

查詢 Java 安裝位置：

```bash
/usr/libexec/java_home
```

將以下內容加入 `~/.zshrc` 或 `~/.bashrc`

```bash
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH=$JAVA_HOME/bin:$PATH
```

重新載入設定：

```bash
source ~/.zshrc
```

確認：

```bash
echo $JAVA_HOME
```

---

# 3. 方法一：使用 IntelliJ IDEA

## 安裝 IntelliJ

下載：

[https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/)

建議使用 **Community Edition（免費版）**

---

## 建立第一個 Java 專案

1. 開啟 IntelliJ
2. 點擊 **New Project**
3. 選擇 **Java**
4. 選擇已安裝的 **JDK**
5. 點擊 **Next → Finish**

---

## 建立 Java Class

在 `src` 目錄下：

```
Right Click → New → Java Class
```

範例：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello Java!");
    }
}
```

執行方式：

```
Right Click → Run
```

---

# 4. 方法二：使用 VS Code

## 安裝 VS Code

下載：

[https://code.visualstudio.com/](https://code.visualstudio.com/)

---

## 安裝 Java Extensions

開啟 **Extensions（Ctrl + Shift + X）**

安裝：

**Extension Pack for Java**

包含：

* Language Support for Java (Red Hat)
* Debugger for Java
* Maven for Java
* Java Test Runner

---

## 建立 Java 專案

開啟 **Command Palette**

```
Ctrl + Shift + P
```

輸入：

```
Java: Create Java Project
```

選擇：

```
No build tools
```

建立檔案：

```
HelloWorld.java
```

範例程式：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello Java!");
    }
}
```

執行：

```
點擊 main() 上方 Run
```

---

# 5. 建議安裝的工具

### Maven（建置工具）

下載：

[https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

確認：

```bash
mvn -version
```

---

### Gradle（另一種建置工具）

下載：

[https://gradle.org/install/](https://gradle.org/install/)

確認：

```bash
gradle -version
```

---

# 6. 建議專案結構

```
project-name
│
├── src
│   └── main
│       └── java
│
├── test
│
├── pom.xml (Maven)
或
build.gradle
```

---

# 7. 常見問題 (Troubleshooting)

### 找不到 Java

執行：

```bash
java -version
```

若找不到，請確認：

* JAVA_HOME 是否設定
* PATH 是否包含 Java

---

### IntelliJ 找不到 JDK

前往：

```
File → Project Structure → SDK
```

手動新增 JDK。

---

### VS Code Java Extension 異常

執行：

```
Java: Clean Java Language Server Workspace
```

重新啟動 VS Code。

---

# 8. Java 版本建議

| 版本      | 狀態      |
| ------- | ------- |
| Java 8  | 舊版本     |
| Java 11 | LTS     |
| Java 17 | LTS（推薦） |
| Java 21 | 最新 LTS  |

---

✅ **推薦開發環境**

* **JDK:** Java 21
* **IDE:** IntelliJ IDEA Community
* **Build Tool:** Maven 或 Gradle

