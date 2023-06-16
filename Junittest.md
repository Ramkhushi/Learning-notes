# JUNIT TESTING 
- [ ] Login to Jenkins Server and Install junit plugin
- Manage Jenkins->Manage Plugins->Click on Available Plugins
- ![image](https://github.com/Ramkhushi/DevOps/assets/120269399/d48eee34-915a-4c96-9523-297872723ec8)
- [ ] Create a new job
      ![image](https://github.com/Ramkhushi/DevOps/assets/120269399/1132fc26-5ed5-4a68-abfc-c480a67fff40)

- [ ] Use the below repo in jenkins source code and select the branch as main
```
https://github.com/Ramkhushi/Java-sample-app.git
```
![image](https://github.com/Ramkhushi/DevOps/assets/120269399/19e7b206-4cf0-4169-ba57-6b7baa2694cf)
![image](https://github.com/Ramkhushi/DevOps/assets/120269399/1db7bee2-c075-4df3-bcfe-fd672433719d)
![image](https://github.com/Ramkhushi/DevOps/assets/120269399/9aaeeb43-f60a-4f58-b5c8-317d7be948d2)
![image](https://github.com/Ramkhushi/DevOps/assets/120269399/1ba93093-48eb-4afe-bbcc-742d5a7f615e)




# Create your own Maven Project 
- [ ] Create a maven project using below command.
```
 mvn archetype:generate -DgroupId=jenkinsDemo -DartifactId=jenkinsDemo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
- [ ] Move to the newly created project
```
cd jenkinsDemo
```
- [ ] Remove main src
```
rm src/main/ -rf
```
- [ ] Create a new test file 
```
vi  src/test/java/JenkinsDemo.java
             import org.junit.After;
import org.junit.Assert;
import org.junit.Before;
import org.junit.Ignore;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

/**
 * Created by 
 * Sample junit test code to integrate by
 */
public class JenkinsDemo
{
    private static String Base_Url = "https://www.facebook.com";
    private WebDriver driver;

    @Before
    public void setUp()
    {
        driver = new ChromeDriver();
        driver.get(Base_Url);
    }

    @After
    public void after()
    {
        driver.quit();
    }

    @Test
    public void testCasePassed()
    {
        Assert.assertTrue(driver.findElement(By.xpath("//form[@id='login_form']")).isDisplayed());
    }

    @Test
    public void testCaseFailed()
    {
        Assert.assertTrue(driver.findElement(By.xpath("//form[@id='failed case']")).isDisplayed());
    }

    @Ignore
    @Test
    public void testCaseIgnored()
    {
        Assert.assertTrue(driver.findElement(By.xpath("//form[@id='ignored case']")).isDisplayed());
    }
}
```

- [ ] remove extra files 
```
 rm -r  src/test/java/jenkinsDemo
```

- [ ] Move to the main project now
```
 cd ../../../
```
- [ ] Edit pom.xml
```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>jenkinsDemo</groupId>
  <artifactId>jenkinsDemo</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>jenkinsDemo</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
     </dependency>
    <dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>3.10.0</version>
  </dependency>
  </dependencies>
</project>
```

- [ ] Run unit test
```
mvn test
```



