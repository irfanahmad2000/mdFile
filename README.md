# Selenium automation
![Alt Text](https://static.javatpoint.com/tutorial/selenium/images/selenium-webdriver-architecture.png)
-

# Table of Contents

[What is Selenium](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#what-is-selenium-1)
-
[Automation Testing](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#automation-testing-1)
-
[Test Automation for Web Applications ](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#automation-testing-1)
-
[Configuring Selenium in Eclipse ](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#configuring-selenium-in-eclipse)
-
[Install Java Development Kit (JDK) ](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#install-java-development-kit-jdk)
-
[Download WebDriver](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#download-webdriver-1)
-
[Create a Project](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#create-a-project-1)
-

[Locators in Selenium](https://github.com/irfanahmad2000/mdFile/blob/main/README.md#locators-in-selenium-1)
-
# What is Selenium
Selenium is one of the most widely used open source Web UI (User Interface) automation testing suite.It was originally developed by Jason Huggins in 2004 as an internal tool at Thought Works. Selenium supports automation across different browsers, platforms and programming languages.
Selenium can be easily deployed on platforms such as Windows, Linux, Solaris and Macintosh. Moreover, it supports OS (Operating System) for mobile applications like iOS, windows mobile and android.
Selenium supports a variety of programming languages through the use of drivers specific to each language.Languages supported by Selenium include C#, Java, Perl, PHP, Python and Ruby.Currently, Selenium Web driver is most popular with Java and C#. Selenium test scripts can be coded in any of the supported programming languages and can be run directly in most modern web browsers. Browsers supported by Selenium include Internet Explorer, Mozilla Firefox, Google Chrome and Safari.
![Alt Text](https://static.javatpoint.com/tutorial/selenium/images/selenium-what-is-selenium.png)

# Automation Testing
Automation testing uses the specialized tools to automate the execution of manually designed test cases without any human intervention. Automation testing tools can access the test data, controls the execution of tests and compares the actual result against the expected result. Consequently, generating detailed test reports of the system under test.
Automation testing covers both functional and performance test on an application.
 # Test Automation for Web Applications 

If we take a look at the type of software applications prevailing in current market scenario, most of the software applications are written as web-based applications to be run in an internet browser. The testing strategy for web-based applications varies widely among companies and organizations.In an era of highly interactive and responsive software processes where many organizations are using some form of agile methodology, test automation is frequently becoming a requirement for software projects.

![Alt Text](https://static.javatpoint.com/tutorial/selenium/images/selenium-webdriver-architecture.png)
# Configuring Selenium in Eclipse

### Install Eclipse IDE
Visit the official Eclipse website at www.eclipse.org.
Navigate to the download section and select the appropriate version of Eclipse IDE for Java Developers.
Choose the version compatible with your platform (Windows, macOS, Linux).
Download and install Eclipse IDE following the provided instructions for your platform.


![Alt Text](https://www.automationtestinghub.com/images/java/eclipse-ide-2022-12-download-page.png)

# Install Java Development Kit (JDK)
Visit the official Oracle website at www.oracle.com.
Navigate to the Java SE Downloads page.
Choose the latest version of the Java Development Kit (JDK) suitable for your operating system.
Select the appropriate download link for your operating system (Windows, macOS, Linux).
Follow the provided instructions to download and install the JDK on your system.

![Alt Text](https://media.geeksforgeeks.org/wp-content/uploads/20220622114149/Step1DownloadingJDKforWindows.png)

# Download WebDriver:
Selenium WebDriver is the most important component of Selenium Tool's Suite. 
Most commonly used WebDriver's include:
Google Chrome Driver
Internet Explorer Driver
Opera Driver
Safari Driver

# Google WebDriver:
Chrome browser implements the WebDriver protocol using an executable called ChromeDriver.exe. This executable start a server on your system which in turn is responsible for running your test scripts in Selenium.

### To download the correct version of ChromeDriver for your system, you can follow these steps:

Open your web browser and go to https://chromedriver.chromium.org.
On the ChromeDriver website, locate the section for downloading ChromeDriver.
Choose the appropriate version of ChromeDriver based on your Chrome browser version and operating system.
Click on the download link to download the ChromeDriver executable file.
Once the download is complete, extract the downloaded file if necessary.
Ensure that the ChromeDriver executable is accessible and its location is known, as you'll need to specify this location in your Selenium code.

![Alt Text](https://www.automationtestinghub.com/images/selenium/chrome-for-testing-availability-stable-beta-dev-canary.png)

# Create a Project

Open Eclipse IDE.
Go to File > New > Other.
In the "Select a wizard" dialog, expand the "Maven" folder.
Select "Maven Project" and click "Next".
Ensure that "Create a simple project (skip archetype selection)" is selected and click "Next".
Enter the Group ID, Artifact ID, and Version for your Maven project. These are used to uniquely identify your project.
Click "Finish" to create the Maven project.



Open Eclipse IDE.
Go to File > New > Other.
In the "Select a wizard" dialog, expand the "Maven" folder.
Select "Maven Project" and click "Next".
Ensure that "Create a simple project (skip archetype selection)" is selected and click "Next".
Enter the Group ID, Artifact ID, and Version for your Maven project. These are used to uniquely identify your project.
Click "Finish" to create the Maven project.


## Project 
### pic (1)

![Screenshot 2024-02-26 214039](https://github.com/irfanahmad2000/mdFile/assets/118617436/3731ae94-ea25-459e-94ef-eafebd72a2b0)

### pic (2)


![Screenshot 2024-02-26 214059](https://github.com/irfanahmad2000/mdFile/assets/118617436/fe70aac1-26a8-4730-b837-0fa966bc892b)

## pom.xml File



![Screenshot 2024-02-26 214132](https://github.com/irfanahmad2000/mdFile/assets/118617436/5aa5715f-5a7e-4c35-bfd8-879399eb1486)


## chrome driver

![Screenshot 2024-02-26 214207](https://github.com/irfanahmad2000/mdFile/assets/118617436/e6acb6ce-d47e-4110-8b1d-72c549da4fdc)

# Code

package com.demo;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.AfterSuite;
import org.testng.annotations.BeforeSuite;
import org.testng.annotations.Test;
public class LoginPage {
	WebDriver driver = null;
	@BeforeSuite
	public void doSetUp() {
		System.setProperty("webdriver.chrome.driver", "./drivers/chromedriver.exe");
		driver = new ChromeDriver();
		driver.get("https://practicetestautomation.com/practice-test-login/");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
}
	@Test
	public void loginForm() throws InterruptedException {
		WebElement username = driver.findElement(By.cssSelector("[id=\"username\"]"));
		username.sendKeys("student");
		
		WebElement password = driver.findElement(By.cssSelector("[id=\"password\"]"));
		password.sendKeys("Password123");
	}
}


# The browser opened and navigated to the specified URL:


![Screenshot 2024-02-26 214912](https://github.com/irfanahmad2000/mdFile/assets/118617436/20f72bd7-816d-4e39-a9c4-d83e28835edf)


# Locators in Selenium

## Locate Elements by CSS ID
This is by far the simplest method of locating an element. The CSS ID, stored in the id attribute of an HTML DOM element, is unique for every element in the page by design. Thus, an ID can uniquely identify an element.
### WebElement button=driver.findElement(By.cssSelector("[id=\"login-button\"]"));

## Locate Elements by CSS Class
A second strategy for locating elements on a page is to search by the class name. The class name is stored in the class attribute of an HTML tag. By design, a CSS class applies to a group of DOM elements.

## Locate Elements by Name
In HTML5, form elements often have a name attribute associated with them. The .find_element_by_name() method only returns the first element with the matching class. If multiple elements of the same name exist, the first matched element will be returned. No matching elements result in a NoSuchElementException error.

## Locate Elements by XPath
If one has failed to identify an element by ID, class, or name, one would need to locate the element through its XML path.
We will use the .find_element_by_xpath() method to locate an appropriate element in the document. The argument that the .find_element_by_xpath() method takes is the path to the element.

## Locate Elements by tagName
One can locate elements by their HTML tag name using the .find_element_by_tag_name() method.
### page_heading = driver.find_element_by_tag_name('h1')

##  Locate Elements by linkText
One can also search for a hyperlink element using the link text. One can either use the .find_element_by_link_text() method to search for the exact link’s text.
Exact Link Text
### click_here_link = driver.find_element_by_link_text('Click Here')


## Locate Elements by partialLinkText
Or one can also search for a hyperlink element using the partial link text .find_element_by_partial_link_text() method to search for a partial text.
Partial Link Text 
### click_here_link = driver.find_element_by_partial_link_text('Click')












