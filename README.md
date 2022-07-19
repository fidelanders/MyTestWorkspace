# MyTestWorkspace - Selenium Exposed!

## What is Selenium?
Selenium is a portable framework and a popular tool for web app testing. It is compatible with multiple programming languages such as Python, C#, and Java. You can use those languages to perform various tasks with Selenium, such as creating a test script. Still, most users prefer to use Java with this framework because it’s more user-friendly than the rest. 

Selenium is not a single software application. It is a suite of various tools that you can use to perform different sorts of testing. 

Selenium has the following tools in its suite:
- Selenium IDE (Integrated Development Environment)
- Selenium WebDriver
- Selenium Client API
- Selenium Remote Control (Deprecated)
- Selenium Grid

Selenium is among the prominent technologies in the automation section of web testing. By using Selenium properly, you can make your testing process quite efficient and complete multiple tasks within a small amount of time.

Jason Huggins created Selenium in the year 2004. He wanted to automate the repetitive manual testing process, so he made a JavaScript program. That same program became the Selenium Core. Apart from Jason, many other developers contributed to creating the Selenium suite.

## Why it’s called Selenium
Selenium derives its name from a joke. At the time of its development, there was another major automated testing framework named Mercury Interactive. Jason jokingly suggested the Selenium to his friends because Selenium is a popular antidote for Mercury poisoning. His friends accepted the suggestion and gave it the name it has now. 

## Features of Selenium
Selenium has many features; the most prominent ones are the following:
- Selenium is compatible with almost all major browsers of the industry, including Chrome, Opera, Safari, etc.
- This suite has a specific group of commands which are called Selenese. They hold the sequence of every Selenium command.
- You can locate elements on a web page through Selenium’s element locators. 
- You cannot use Selenium to test desktop applications or mobile apps. You can only use it for web app testing. 


## What is Maven?
Maven is an automation tool that developers mostly use for Java projects. Apart from Java, you can use it with several other programming languages such as C#, Scala, Ruby, etc. It’s a product of the Apache Software Foundation, so it is an open-source tool. 

Maven makes the build process much more straightforward and provides you with a uniform build system. It ensures that Java developers follow the best development practices while working on Java projects. It entered the industry in the year 2002, and since then, it has become one of the most significant Apache projects. 

Maven derives its name from the Yiddish word ‘maven,’ which means “accumulator of knowledge.” 

## Features of Maven
- Maven ensures consistency among various projects
- It simplifies project setup by providing the boilerplate for modules or projects
- Can work with several projects at once
- Maven can build any quantity of projects into its specific output types such as a WAR or JAR without requiring scripting in many cases
- It is based on the POM (project object model)

Now that we have exposed Selenium and Maven let’s understand the Eclipse IDE. Having a working knowledge of these three is crucial if you want to work on a Selenium project with Eclipse. 

## What is the Eclipse IDE?
Eclipse is an IDE (integrated development environment) that helps developers work with Selenium and related technologies. You can use Eclipse to develop applications in C++, Ruby, Python, C, Perl, Java, etc. 

## Features of the Eclipse IDE
- It is an open-source tool, which means you can use it for free.
- The foundational platform of the Eclipse IDE has multiple plugins and can be extended with more plugins. 
- You can convert Eclipse into an IDE for any programming language by using its respective plugin.
- The JDT (Java Development Tools) project gives a plugin to use Eclipse as a Java IDE. Similarly, PyDev is a plugin that allows you to use Eclipse as a Python IDE.
- You can use the Eclipse platform and its plugins to create IDEs, client applications, etc. 
- How to Create a Selenium Project with Eclipse IDE
- In this section of our article, we’ll look at how you can create a Selenium project with Eclipse. It’s the first step of working on a Selenium project, and many beginners struggle with it. 

You’d need to have Maven and TestNG installed in your system before you can create a Selenium project through Eclipse. Ensure that you install them (Maven and TestNG) before you begin this process.

**_Step #1:_** Open Eclipse and right-click on the Package Explorer section. You’d see a menu pop-up. Select the ‘New’ button, which will open another menu to select the “Other…” option.  

**_Step #2:_** When you’d click the “Other…” button, it would open a new window. Select the Maven Project and then click on the ‘Next’ button. 

**_Step #3:_** A new window will appear now. Here, you have to tick the ‘Create a simple project (skip archetype selection)” box. After that, select the “Next” button. 

**_Step #4:_** In this section, you’d have to enter the Group Id and the Artifact Id. They both are vital for the naming of your project. The Group Id will help you identify your project across all the other ones. It must follow the package name rules. This means it should start with a reverse domain name you control. Maven doesn’t enforce this naming rule; however, due to the tool’s vast popularity, it has become a common practice to follow this rule. You can make multiple subgroups with a Group Id as well. 

The Artifact Id is the name of your jar without a version. If you are its creator, you can choose any name you want as long as you don’t use any strange symbols and only use lowercase letters.  

Keep the above points in mind while entering the Group Id and Artifact Id for your project. Once you have entered these details, click on the “Finish” button.

**_Step #5:_** Let’s add the necessary dependencies to the POM file for our project. Head to the pom.xml file and select the ‘pom.xml’ tab in Eclipse. Now, add the dependencies related to TestNG and Selenium WebDriver.

**_Step #6:_** In this step, get a testng.xml file by creating a TestNG class. Copy the following code in this file:

### 
{
  package tests;

  import org.openqa.selenium.WebDriver;
  import org.openqa.selenium.firefox.FirefoxDriver;
  import org.testng.annotations.Test;
  import org.testng.annotations.BeforeClass;
  import org.testng.annotations.AfterClass;

  public class NewTest {

  public WebDriver driver;

  @Test
  public void openMyBlog() {

    driver.get(“https://www.softwaretestingmaterial.com/”);

  }

  @BeforeClass
  public void beforeClass() {

  System.setProperty(“webdriver.gecko.driver”, “D:\\Selenium\\Drivers\\geckodriver.exe”);

  driver = new FirefoxDriver();

  }

  @AfterClass
  public void afterClass() 
  {
  
  driver.quit();
  
  }
  }
}

**_Step #7:_** Now you can run your Selenium project with Eclipse by using the TestNG file. 

**NB:** Make sure that you understand the above tutorial before you move onto the next one.


# Selenium Project with Eclipse: An Example
Here, we have shared the code for a flight-booking solution based on Selenium. The software selects the arrival and departure locations for the flight along with the date of the same. This tool performs these tasks on the MakeMyTrip website. 

You can take inspiration from this project to create a similar Selenium project with Eclipse yourself. If you haven’t worked on a Selenium project before, we suggest working on a smaller version of this project first.

For example, you can create a program that selects the arrival and departure locations only. On the other hand, if you want to expand on this project, you can add more functionalities. 

##### The Browser
{
  package browser;

  import org.openqa.selenium.WebDriver;
  import org.openqa.selenium.chrome.ChromeDriver;
  
  public class BrowserSelection 
  {
  static WebDriver driver;
  
  public static WebDriver UsingChrome() {
  System.setProperty(“webdriver.chrome.driver”, “E:\\SeleniumLibs\\\\chromedriver_win32\\chromedriver.exe”);
  
  driver = new ChromeDriver();
  driver.manage().window().maximize();
  return driver;
  }
  }

}

#### The Code
{
  package makemytrip;
  
  import java.awt.AWTException;
  import java.awt.Robot;
  import java.awt.evenMakeMyTrip  import java.util.List;
  import java.util.concurrent.TimeUnit;
  import org.openqa.selenium.By;
  import org.openqa.selenium.JavascriptExecutor;
  import org.openqa.selenium.WebDriver;
  import org.openqa.selenium.WebDriverException;
  import org.openqa.selenium.WebElement;
  import org.testng.annotations.AfterMethod;
  import org.testng.annotations.BeforeMethod;
  import org.testng.annotations.Test;
  import browser.BrowserSelection;
  
  
  public class MakeMyTripProject 
  {
  WebDriver driver;
  
  @BeforeMethod
  public void OpenBrowser()
  {
    driver = BrowserSelection.UsingChrome();
  }
  
  @Test
  public void TripDetails() throws InterruptedException, AWTException
  {
    driver.get(“https://www.makemytrip.com/”);
    driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
    Thread.sleep(5000);
    
    try 
        {
        /* 
        String frameStatus = driver.findElement(By.id(“webklipper-publisher-widget-container-notification-frame”)).getTagName();
        System.out.println(frameStatus);
        driver.switchTo().frame(“notification-frame-31764456”);
        driver.findElement(By.xpath(“.//*[@id=’webklipper-publisher-widget-container-notification-close-div’]/i”)).click();
        driver.switchTo().defaultContent();
        Thread.sleep(3000); 
        */

        driver.findElement(By.xpath(“//input[@id=’hp-widget__sfrom’]”)).click();
        driver.findElement(By.xpath(“//input[@id=’hp-widget__sfrom’]”)).clear();

        //driver.findElement(By.xpath(“//input[@id=’hp-widget__sfrom’]”)).sendKeys(“Goa”);
        Thread.sleep(2000);

        List<WebElement> fromCities = driver.findElements(By.xpath(“//ul[@id=’ui-id-1′]/li/div/p/span[1]”));

        System.out.println(fromCities.size()+”\n”);

        for(int i=0;i<fromCities.size();i++)
        {
        WebElement element=fromCities.get(i);
        System.out.println(element.getAttribute(“innerHTML”));
        }

        //driver.findElement(By.xpath(“//ul[@id=’ui-id-1′]/li/div/p/span”)).click();
        driver.findElement(By.xpath(“//li[contains(@aria-label,’Top Cities : Goa, India ‘)]/div/p/span[1]”)).click();
        driver.findElement(By.xpath(“//input[@id=’hp-widget__sTo’]”)).click();
        driver.findElement(By.xpath(“//input[@id=’hp-widget__sTo’]”)).clear();

        //driver.findElement(By.xpath(“//input[@id=’hp-widget__sTo’]”)).sendKeys(“Mumbai”);
        Thread.sleep(2000);

        List<WebElement> toCities = driver.findElements(By.xpath(“//ul[@id=’ui-id-2′]/li/div/p/span[1]”));
        System.out.println(toCities.size()+”\n”);

        for(int i=0;i<toCities.size();i++)
        {
        WebElement element=toCities.get(i);
        System.out.println(element.getAttribute(“innerHTML”));
        }

        //driver.findElement(By.xpath(“//ul[@id=’ui-id-2′]/li/div/p/span”)).click();

        driver.findElement(By.xpath(“//ul[@id=’ui-id-2′]/li[3]/div/p/span[1]”)).click();
        Thread.sleep(2000);
    
        driver.findElement(By.xpath(“//input[@id=’hp-widget__depart’]”)).click();
        Thread.sleep(2000);

        String date = “10-OCTOBER-2018”;
        String splitter[] = date.split(“-“);
        String month_year = splitter[1];
        String day = splitter[0];
        
        System.out.println(month_year);

        System.out.println(day);

        selectDate(month_year,day);

        Thread.sleep(3000);

        driver.findElement(By.xpath(“//button[@id=’searchBtn’]”)).click();
        Thread.sleep(5000);
        Thread.sleep(2000);

        JavascriptExecutor js = (JavascriptExecutor) driver;
        js.executeScript(“window.scrollBy(0,3000)”);
        
        /*
        Robot robot = new Robot();
        robot.keyPress(KeyEvent.VK_PAGE_DOWN);
        robot.keyRelease(KeyEvent.VK_PAGE_DOWN);*/
        Thread.sleep(5000);
        driver.findElement(By.xpath(“//div[@id=’aln_AI_dep’]/span[3]”)).click();
        Thread.sleep(5000);
        
        List<WebElement> flights = driver.findElements(By.xpath(“//div[@class=’top_first_part clearfix’]/div/span/span[2]/span[1]”));
        System.out.println(“No. of Air India flight search results: —“+flights.size());
    
    }catch(WebDriverException e)
    {
    System.out.println(“Exception is: —“+e+”\n”);
    }
    }
  
    public void selectDate(String monthyear, String Selectday) throws InterruptedException
    {
    List<WebElement> elements = driver.findElements(By.xpath(“//div[@class=’ui-datepicker-title’]/span[1]”));
  
    for (int i=0; i<elements.size();i++)
    {
    System.out.println(elements.get(i).getText());
  
    //Selecting the month
    if(elements.get(i).getText().equals(monthyear))
    {
    //Selecting the date
    List<WebElement> days = driver.findElements(By.xpath(“//div[@class=’ui-datepicker-inline ui-datepicker ui-widget ui-widget-content ui-helper-clearfix   ui-corner-all ui-datepicker-multi ui-datepicker-multi-2′]/div[2]/table/tbody/tr/td/a”));
  
    for (WebElement d:days)
    {
    System.out.println(d.getText());

    if(d.getText().equals(Selectday))
    {
    d.click();
    Thread.sleep(10000);

    return;

    }
    }
    }
    }

    driver.findElement(By.xpath(“//div[@class=’ui-datepicker-inline ui-datepicker ui-widget ui-widget-content ui-helper-clearfix ui-corner-all ui-datepicker-multi ui-datepicker-multi-2′]/div[2]/div/a/span”)).click();

    selectDate(monthyear,Selectday);

    }

    @AfterMethod
    public void CloseBrowser()
    {
    driver.quit();
    }
    }
 }
