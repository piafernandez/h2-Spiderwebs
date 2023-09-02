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

## A03:2021 – Injection

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

   <img width="335" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/73966a5a-e81f-453f-a88b-791dfb9e1b91">


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

   <img width="314" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/cac24652-7166-4859-abcb-062fdc66e7a9">


5. Download Webgoat 8

   ```
   $ wget https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/webgoat-server-8.0.0.M26.jar
   ```

   <img width="332" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/2f88e095-04a4-4bf1-9442-61ba9b5b00c4">


6. Run Webgoat 8

   ```
   $ java -jar webgoat-server-8.0.0.M26.jar
   ```

   <img width="410" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/0d94d7ef-5542-4106-8831-0dcc6d36fcb0">


7.  Open Webgoat in browser with this url: http://localhost:8080/WebGoat/

8. Register as a new user

   <img width="373" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/2cdad89b-9c73-4db6-a7ab-a567572589b1">


9. Now you can start hacking ! (safely)

   <img width="424" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/8bf8a11d-bc3f-4076-b4c0-890e4d46eb0e">




# 3. F12. Solve Webgoat 8: General: Developer tools.

## First steps

1. Click on General > Developer Tools to have the instructions

<img width="434" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/60ad6802-b0a2-4db5-839b-223fff62c219">


2. To open the developer tools you can do one of the choices below

   ```
   1. right click anywhere from the browser and select "Inspect"
   2. click "f12" on your keyboard (sometimes you need to click on the key "fn" then "f12")
   ```

3. Click on the numbers to continue the task

  <img width="174" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/4684caf4-d353-40b8-b0b0-ef67ee52d538">


4. Elements tab: allows you to look at the HTML and CSS code

   <img width="410" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/6ad6bc5c-d8de-452d-a560-82aca5ba8112">


5. Console tab

   1. Clear the console: CTRL + L or click on the trash can

      <img width="397" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/7297e3b2-db52-4fe4-8623-d92a0d82164f">


   2. You can write your own JavaScript

      > you can ignore the undefined this statement, it just says that the function you used did not return anything. 
      >
      > This did not happen to (1+3) as the function returned 4

     <img width="395" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/3d680f6a-9a32-46c7-aa92-49473a96d4c7">


6. Sources tab: you can check out the file system and wiew all HTML, CSS and JavaScript files that are used to create the website.

   ```
   Click on Debugger > Sources
   ```

   <img width="413" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/813ff4e8-3ec8-42a8-8c0c-3a53276e8a19">


7. Network tab: you can view HTTP requests and responses the website has performed

  <img width="415" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/5bfd3579-3be2-4668-91d3-a45597d73601">


## Let's try it !

### Console

<img width="333" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/3d99afba-a400-4d4c-aa56-b4fb34c147f1">


1. write this in your console

   ```
   webgoat.customjs.phoneHome()
   ```

2. copy and paste the most recent number in the field

  <img width="415" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/2473b85c-53a7-4e47-9281-f70c8617d162">


3. This means it worked !

   <img width="134" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/744aded9-3444-4dcb-96ea-80696f7449d6">


### Network

<img width="336" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/98675850-037e-43fb-96dd-52292875fd44">


1. Click on the Go button above

2. Then click on the highlighted parts and copy then paste the networkNum

   <img width="422" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/cea251a0-e520-4076-894e-950a00f8b5fe">


3. This means it worked

   <img width="233" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/421c0447-e508-4f53-ab61-51abf1279335">

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

<img width="401" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/81ffeb79-4336-4b2b-bf60-3269d0b719ff">


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

   <img width="416" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/bca73854-e8c4-4d7f-b10f-d73240b15c1a">


2. Click on a category, here I have clicked on "Accessories"

   Here is the url: https://0a59008003193495d93876050029002e.web-security-academy.net/filter?category=Accessories

  <img width="415" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/ab8c1066-6bf3-4723-bc77-2164edc91c30">

3. Modify the `category` parameter in the url, giving it the value `'+OR+1=1--`

   https://0a59008003193495d93876050029002e.web-security-academy.net/filter?category=Accessories%27+OR+1=1--

4. Now you can see all the hidden products !

<img width="447" alt="image" src="https://github.com/piafernandez/h2-Spiderwebs/assets/71267247/b048ef09-b41b-4b99-869a-0c6315e4df14">


# Sources and links

- *A05 Security Misconfiguration - OWASP Top 10:2021*. https://owasp.org/Top10/A05_2021-Security_Misconfiguration/. Accessed 30 Aug. 2023.
- *A06 Vulnerable and Outdated Components - OWASP Top 10:2021*. https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/. Accessed 30 Aug. 2023.
- *A03 Injection - OWASP Top 10:2021*. https://owasp.org/Top10/A03_2021-Injection/. Accessed 30 Aug. 2023.
- *Install Webgoat 8 - Learn Web Pentesting*. https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/. Accessed 30 Aug. 2023.
- *ChatGPT - OpenAI* [ChatGPT (openai.com)](https://chat.openai.com/?model=text-davinci-002-render-sha) Accessed 30 Aug. 2023.
- *SQLZOO*. https://sqlzoo.net/wiki/SQL_Tutorial. Accessed 2 Sept. 2023.
- *Read the Notes about This Table. - SQLZOO*. https://sqlzoo.net/wiki/Read_the_notes_about_this_table. Accessed 2 Sept. 2023.
- *Lab: SQL Injection Vulnerability in WHERE Clause Allowing Retrieval of Hidden Data | Web Security Academy*. https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data. Accessed 2 Sept. 2023.
