// Step 1: Install Required Tools
// - Install Java JDK: https://www.oracle.com/java/technologies/javase-downloads.html
// - Set JAVA_HOME and add it to PATH
// - Install Eclipse or IntelliJ IDEA
// - Download ChromeDriver: https://sites.google.com/chromium.org/driver/
//   Match your Chrome browser version and extract to: C:\selenium\drivers

// Step 2: Download Selenium Java JARs
// - From: https://www.selenium.dev/downloads/
// - Extract and include all JARs and lib JARs in your project

// Step 3: Java Code using Selenium and ChromeDriver

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class CommonTest {
    public static void main(String[] args) {
        // Set path to ChromeDriver executable
        System.setProperty("webdriver.chrome.driver", "C:\\selenium\\drivers\\chromedriver.exe");

        // Initialize ChromeDriver
        WebDriver driver = new ChromeDriver();

        // Maximize browser window
        driver.manage().window().maximize();

        // Open Google
        driver.get("https://www.google.com");

        // Find search box, type text, and submit
        WebElement searchBox = driver.findElement(By.name("q"));
        searchBox.sendKeys("Selenium WebDriver");
        searchBox.submit();

        // Wait and print title
        try {
            Thread.sleep(3000);  // Wait for 3 seconds
            String title = driver.getTitle();
            System.out.println("Page Title: " + title);
        } catch (Exception e) {
            e.printStackTrace();
        }

        // Close browser
        driver.quit();
    }
}

// Step 4: Run the program
// - In Eclipse: Right-click file > Run As > Java Application
// - In IntelliJ: Click the green play button

// Optional: Add "C:\selenium\drivers" to your Windows PATH to avoid repeating System.setProperty line.
