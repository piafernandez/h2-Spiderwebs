# Table of contents

1. OWASP 10 2021 - Summaries
   - [A05:2021-Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
   - [A06:2021-Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
   - [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)
2. Goat. [Install webgoat](https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/)
3. F12. Solve Webgoat 8: General: Developer tools.
4. Not outdated. Update all operating system and all applications in your Linux.
5. Sequel. Solve SQLZoo:
   - 0 SELECT basics
   - 2 SELECT from World, from first two subtasks.
6. Johnny tables. Solve Portswigger Labs: [Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data)

# 1. OWASP 10 2021

## A05:2021 – Security Misconfiguration

> https://owasp.org/Top10/A05_2021-Security_Misconfiguration/

- 90% of applications were tested for misconfiguration vulnerabilities with an average incidence rate of 4%
- An application is considered vulnerable when:
  - it's missing appropriate security or misconfigured permissions on cloud services
  - unnecessary features are enabled or installed
  - default accounts and their passwords are still enabled and unchanged
- How to prevent:
  - Configure development, QA and production environments identically with different credentials for each environment
  - Install only necessary features and frameworks
  - Have an automated process that verifies the effectiveness of the configurations and settings in all environments
- Example Attack Scenario
  - If the applications server's configuration allows detailed error messages. This can potentially expose sensitive information to everyone

## A06:2021 – Vulnerable and Outdated Components

> https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/

- Known issue that have a hard time to test and assess the risk
- You are vulnerable if:
  - you are not aware the versions of all components and the dependencies that you use
  - your OS and applications are out of date, vulnerable or unsupported
  - you don't regularly scan for vulnerabilities 
  - you don't secure the components' configurations
- How to prevent:
  - remove unused dependencies, unnecessary features and components
  - create a version inventory of your components and dependencies
- Example Attack Scenario
  - Component flaws can lead to severe impact due to shared privileges

# A03:2021 – Injection

> https://owasp.org/Top10/A03_2021-Injection/

- 94% of the applications were tested for some form of injection with a max incidence rate of 19%, an average incidence rate of 3%, and 274k occurrences
- An application is considered vulnerable when:
  - data is not validated, filtered or sanitized by the application
  - data given by the users are directly used as parameters to extract additional records
- Mos common injection are SQL, NOSQL
- How to prevent:
  - reviewing source code is the best way to detect possible injections
  - automate testing of headers, URL, cookies, JSON, xml
  - use a safe API which will avoid the usage of the interpreter and will provide a parameterize interface
- Example Attack Scenario
  - if you have an application that uses untrusted data in the construction of the SQL query

# 2. Install webgoat

> https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/
>
> Webgoat is a practice target for web penetratrion testing.

## Steps

1. Open your virtual machine

2. Open you terminal

   <img src="C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902132724723.png" alt="image-20230902132724723" style="zoom:67%;" />

3. Install Java and other helpful tools:

   ```
   $ sudo apt-get update
   $ sudo apt-get -y install openjdk-17-jre ufw wget bash-completion
   ```

   ```
   sudo: used to execute a command with admin privileges
   
   apt-get: used for managing software packages on Debian-based Linux distributions
   
   -y: used to automatically answer "yes" to any prompts or confirmations that may come up during the installation process
   
   openjdk-17-jre: first package you want to install, which is used to run Java applications
   
   ufw: second package you want to install, for managing firewall rules on Linux systems
   
   wget: third package you want to install. It is a command-line utility for downloading files from the internet
   
   bash-completion: fourth package you want to install. It provides enhanced tab-completion support for the Bash shell
   ```

4. Enable the firewall

   ```
   $ sudo ufw enable
   ```

   ![image-20230902133547154](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902133547154.png)

5. Download Webgoat 8

   ```
   $ wget https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/webgoat-server-8.0.0.M26.jar
   ```

   <img src="C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902133950245.png" alt="image-20230902133950245" style="zoom:67%;" />

6. Run Webgoat 8

   ```
   $ java -jar webgoat-server-8.0.0.M26.jar
   ```

   ![image-20230902134203409](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902134203409.png)

7.  Open Webgoat in browser with this url: http://localhost:8080/WebGoat/

8. Register as a new user

   ![image-20230902134527263](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902134527263.png)

9. Now you can start hacking ! (safely)

   ![image-20230902134755266](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902134755266.png)



# 3. F12. Solve Webgoat 8: General: Developer tools.

## First steps

1. Click on General > Developer Tools to have the instructions

![image-20230902134952006](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902134952006.png)

2. To open the developer tools you can do one of the choices below

   ```
   1. right click anywhere from the browser and select "Inspect"
   2. click "f12" on your keyboard (sometimes you need to click on the key "fn" then "f12")
   ```

3. Click on the numbers to continue the task

   ![image-20230902140159983](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902140159983.png)

4. Elements tab: allows you to look at the HTML and CSS code

   ![image-20230902143036158](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902143036158.png)

5. Console tab

   1. Clear the console: CTRL + L or click on the trash can

      ![image-20230902143329209](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902143329209.png)

   2. You can write your own JavaScript

      > you can ignore the undefined this statement, it just says that the function you used did not return anything. 
      >
      > This did not happen to (1+3) as the function returned 4

      ![image-20230902143549899](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902143549899.png)

6. Sources tab: you can check out the file system and wiew all HTML, CSS and JavaScript files that are used to create the website.

   ```
   Click on Debugger > Sources
   ```

   ![image-20230902144546221](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902144546221.png)

7. Network tab: you can view HTTP requests and responses the website has performed

   ![image-20230902144832739](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902144832739.png)

## Let's try it !

### Console

![image-20230902143827989](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902143827989.png)

1. write this in your console

   ```
   webgoat.customjs.phoneHome()
   ```

2. copy and paste the most recent number in the field

   ![image-20230902144115775](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902144115775.png)

3. This means it worked !

   ![image-20230902144152475](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902144152475.png)

### Network

![image-20230902144900124](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902144900124.png)

1. Click on the Go button above

2. Then click on the highlighted parts and copy then paste the networkNum

   ![image-20230902145307178](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902145307178.png)

3. This means it worked

   ![image-20230902145615177](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902145615177.png)

# 4. Not outdated. Update all operating system and all applications in your Linux.

## Steps

> You can update all software in Linux by following the steps below:

1. Open your virtual machine

2. Open your terminal

3. Write this command:

   ```
   $ sudo apt-get update
   ```

4. Then this one:

   ```
   $ sudo apt-get dist-upgrade
   ```

5. **If this is your first full upgrade, reboot (it's only needed for kernel upgrades)**

   > Don't forget to save your work before running this command !

   ```
   $ sudo rebootpia
   ```

# 5. Solve SQL Zoo

> https://sqlzoo.net/wiki/SQL_Tutorial

![image-20230902151928005](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902151928005.png)

## 0 SELECT basics



1. **Modify it to show the population of Germany**

   > `WHERE`

   ```
   SELECT population FROM world
     WHERE name = 'Germany';
   ```

2. Show the **name** and the **population** for 'Sweden', 'Norway' and 'Denmark'.

   > `IN`: allows us to check if an item is in a list

   ```
   SELECT name, population FROM world
     WHERE name IN ('Sweden', 'Norway', 'Denmark');
   ```

3. Modify it to show the country and the area for countries with an area between 200,000 and 250,000.

   > `BETWEEN` allows range checking (range specified is inclusive of boundary values)

   ```
   SELECT name, area FROM world
     WHERE area BETWEEN 200000 AND 250000;
   ```

## 2 SELECT from World, from first two subtasks.

1. Introduction

   ```
   SELECT name, continent, population FROM world
   ```

   ```
   # We can see all the countries with their continent and their population.
   ```

2. Large Countries

   > Show the name for the countries that have a population of at least 200 million.

   ```
   SELECT name FROM world WHERE population >= 200000000;
   ```

   ```
   # I changed to number for the population, and I also changed the operator because it is at least 200000000.
   ```

3. Per capita GDP

   > Give the name and the per capita GDP for those countries with a population of at least 200 million.

   ```
   SELECT name, (gdp/population) FROM world WHERE population >= 200000000;
   ```

   ```
   # I have added "(gdp/population)" to have the result of the calculation for each country. => per capita GDP is the GDP divided by the population
   ```

# 6. Johnny tables. Solve PortSwigger Labs

> [Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data)

## Steps

1.  Open the lab

   <img src="C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902155147985.png" alt="image-20230902155147985" style="zoom:67%;" />

2. Click on a category, here I have clicked on "Accessories"

   Here is the url: https://0a59008003193495d93876050029002e.web-security-academy.net/filter?category=Accessories

   ![image-20230902154623467](C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902154623467.png)

3. Modify the `category` parameter in the url, giving it the value `'+OR+1=1--`

   https://0a59008003193495d93876050029002e.web-security-academy.net/filter?category=Accessories%27+OR+1=1--

4. Now you can see all the hidden products !

<img src="C:\Users\ferna\OneDrive - HESSO\Documents\02_School\00_HAAGA-HELIA\Semester VII\01_Information Security - Tero Karvinen\01_Assignments\h2\h2\image-20230902154756233.png" alt="image-20230902154756233" style="zoom:67%;" />

# Sources and links

- *A05 Security Misconfiguration - OWASP Top 10:2021*. https://owasp.org/Top10/A05_2021-Security_Misconfiguration/. Accessed 30 Aug. 2023.
- *A06 Vulnerable and Outdated Components - OWASP Top 10:2021*. https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/. Accessed 30 Aug. 2023.
- *A03 Injection - OWASP Top 10:2021*. https://owasp.org/Top10/A03_2021-Injection/. Accessed 30 Aug. 2023.
- *Install Webgoat 8 - Learn Web Pentesting*. https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/. Accessed 30 Aug. 2023.
- *ChatGPT - OpenAI* [ChatGPT (openai.com)](https://chat.openai.com/?model=text-davinci-002-render-sha) Accessed 30 Aug. 2023.
- *SQLZOO*. https://sqlzoo.net/wiki/SQL_Tutorial. Accessed 2 Sept. 2023.
- *Read the Notes about This Table. - SQLZOO*. https://sqlzoo.net/wiki/Read_the_notes_about_this_table. Accessed 2 Sept. 2023.
- *Lab: SQL Injection Vulnerability in WHERE Clause Allowing Retrieval of Hidden Data | Web Security Academy*. https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data. Accessed 2 Sept. 2023.
