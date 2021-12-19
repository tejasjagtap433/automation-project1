# automation-project1
package frame;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import configuration.PathConfig;

public class Frame {
	public static void main(String[] args) {
		// Browser configuration

		System.setProperty("webdriver.chrome.driver", PathConfig.driverPath);

		WebDriver driver = new ChromeDriver();

		//driver.get(PathConfig.appUrl);
		
		driver.get("https://www.w3schools.com/js/tryit.asp?filename=tryjs_myfirst");

		driver.manage().window().maximize();
		
		//COntrol will switch to frame
		driver.switchTo().frame("iframeResult");
		
			
		driver.findElement(By.xpath("//button[@type='button']")).click();
		
		//to get control back to main page
		driver.switchTo().defaultContent();
			driver.switchTo().parentFrame();
			
		
