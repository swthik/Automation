# Automation
Automation task 1: flipkart

package com.example;

import java.util.regex.Pattern;
import java.util.concurrent.TimeUnit;
import org.junit.*;
import static org.junit.Assert.*;
import static org.hamcrest.CoreMatchers.*;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.apache.commons.io.FileUtils;
import java.io.File;

public class FlipkartAutomation {
  private WebDriver driver;
  private String baseUrl;
  private boolean acceptNextAlert = true;
  private StringBuffer verificationErrors = new StringBuffer();
  JavascriptExecutor js;

  public void setUp() throws Exception {
    System.setProperty("webdriver.chrome.driver", "");
    driver = new ChromeDriver();
    baseUrl = "https://www.google.com/";
    driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
    js = (JavascriptExecutor) driver;
  }

  public void testFlipkartAutomation() throws Exception {
    driver.get("https://www.flipkart.com/");
    driver.findElement(By.linkText("Login")).click();
    driver.findElement(By.xpath("//input[@value='*****']")).clear();
    driver.findElement(By.xpath("//input[@value='*****']")).sendKeys("*****");
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Get access to your Orders, Wishlist and Recommendations'])[1]/following::form[1]")).click();
    driver.findElement(By.xpath("//div[2]/input")).click();
    driver.findElement(By.xpath("//input[@value='*****']")).clear();
    driver.findElement(By.xpath("//input[@value='*****']")).sendKeys("*****");
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Privacy Policy'])[1]/following::button[1]")).click();
    driver.findElement(By.name("q")).click();
    driver.findElement(By.name("q")).clear();
    driver.findElement(By.name("q")).sendKeys("hp laptop");
    driver.findElement(By.linkText("hp laptopin Laptops")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div[3]/div/div[2]/div[2]/div/div/div/a/div[2]/div/div")).click();
    
    driver.findElement(By.xpath("//div[@id='container']/div/div[3]/div/div/div[2]/div/ul/li/button")).click();
    driver.close();
    
    driver.findElement(By.name("q")).click();
    
    driver.findElement(By.name("q")).clear();
    driver.findElement(By.name("q")).sendKeys("mobiles");
    driver.findElement(By.cssSelector("._2M8cLY")).submit();
    driver.findElement(By.xpath("//div[@id='container']/div/div[3]/div/div[2]/div[5]/div/div/div/a/div[2]/div/div")).click();
    
    driver.findElement(By.xpath("//div[@id='container']/div/div[3]/div/div/div[2]/div/ul/li/button")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div[2]/div/div/div/div/div[3]/div/div/div/div[3]")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div[2]/div/div/div/div/div[3]/div/div[2]/div[2]/div[2]")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div/div/div[3]/div/div[2]")).click();
    driver.close();

    driver.findElement(By.xpath("//div[@id='container']/div/div/div/div[2]/div[5]/div/div/a/div")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div[2]/div/div/div/div/div[2]/div/div/div/div[3]")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div/div/div[2]/div[3]/div")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div/div/div[2]/div[3]/div/div/div/div")).click();
    driver.findElement(By.xpath("//div[@id='container']/div/div/div/div[2]/div[3]/div/div/div[2]/div[2]/div/ul/li[10]/a/div")).click();
    driver.close();
  }

  public void tearDown() throws Exception {
    driver.quit();
    String verificationErrorString = verificationErrors.toString();
    if (!"".equals(verificationErrorString)) {
      fail(verificationErrorString);
    }
  }

  private boolean isElementPresent(By by) {
    try {
      driver.findElement(by);
      return true;
    } catch (NoSuchElementException e) {
      return false;
    }
  }

  private boolean isAlertPresent() {
    try {
      driver.switchTo().alert();
      return true;
    } catch (NoAlertPresentException e) {
      return false;
    }
  }

  private String closeAlertAndGetItsText() {
    try {
      Alert alert = driver.switchTo().alert();
      String alertText = alert.getText();
      if (acceptNextAlert) {
        alert.accept();
      } else {
        alert.dismiss();
      }
      return alertText;
    } finally {
      acceptNextAlert = true;
    }
  }
}
