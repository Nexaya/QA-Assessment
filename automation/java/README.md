# Java Automation Instructions

## Task:
- Write an automated test script using **Java** to test the login functionality of a web-based application.
- Ensure that both valid and invalid login scenarios are covered.

## Requirements:
- Use **Selenium WebDriver** or any other preferred Java automation framework.
- Ensure to include assertions for success and failure scenarios.

## Deliverables:
- Submit your Java code along with instructions to run the test.
- Include any dependencies in a `pom.xml` or `build.gradle` file if using Maven or Gradle.

---

## Sample:
```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;

public class LoginTest {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", "path-to-chromedriver");

        WebDriver driver = new ChromeDriver();
        driver.get("http://example.com/login");

        // Perform login test
        driver.findElement(By.name("username")).sendKeys("valid_username");
        driver.findElement(By.name("password")).sendKeys("valid_password");
        driver.findElement(By.name("login")).click();

        // Assert login success
        String expectedTitle = "Dashboard";
        String actualTitle = driver.getTitle();
        if (expectedTitle.equals(actualTitle)) {
            System.out.println("Login successful");
        } else {
            System.out.println("Login failed");
        }

        driver.quit();
    }
}
