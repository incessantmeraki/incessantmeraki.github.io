---
layout:     post
title:      Setting up Java development environment (1/3)
date:       2015-08-28 00:44:19
summary:    Part one of setting up Java Development Environment.I will install Java Compiler(JDK) and Java Runtime Environment(JRE) on a windows XP machine and set up environment variable Path to point to these locations. 
categories: jekyll pixyll
---

I prefer plain text editor and these three features are the minimum requirements I seek in them.

  * Displaying Line Number
  * Color Coding
  * Automatic indentation

In Linux, Gedit suffices my requirement but Notepad in Windows is just too plain. Notepad++ is one option but I prefer Sublime Text for its smooth learning curve and powerful features. In this article I will show you how to set up a simple but powerful development environment for Java. 

To give you the basic overview, I will be performing the following steps:

  1. Setup Environment variable Path to point to JDK and JRE
  2. Download sublime text and set it up
  3. Compile and run the java program 

I will be performing the above steps in Windows XP. I am using XP for two reasons: It is very basic and if you can set up the environment in XP, I bet you can do it for newer versions of Windows.

###**<span class="mid-gray"> Setting up Java Compiler and Runtime </span>**

We require two java components to compile and run Java programs. Java Compiler and Java runtime environment. Java Compiler converts the code that you write(.java file) into bytecode (.class file). Then java runtime environment runs the bytecode(.class file). Let us see if these are set up in our sytem. 

To do so, *Run command-prompt and give the commands 'javac' and 'java'*. 

![1]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/1.PNG)

You will see the output as above if both of them are not set.There can be two reasons for the above output.

  1. You have not installed Java Development Kit(javac) aka JDK or Java Runtime Environment(java) aka JRE or both in your system.
  2. You have installed them but your system's command prompt does not recognize it.

In my case, I have not installed either of it. So, let me install both of them. I googled *"java oracle download"* and opened the first page that came. 

![2]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/2.PNG)

Click the Download button in blue color below **JDK** and **JRE** and download these two softwares for your operating system. Once, downloaded you will see two installation files. Open those files and install them one by one. 

![3]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/3.PNG)

Once you install both of them, you will see two folders(*jdk and jre*) in the directory **C:\Program Files\Java**

![4]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/4.PNG)

Note down the name of two directores and create a full path string to both directory appending \bin directory to the end as follow:

![5]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/5.PNG)

Now, **right click My Computer** and under Advanced tab click Environment Variables.

![6]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/6.PNG)


Once, Environment Variables windows is loaded, select Click the *new* button.

![7]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/7.PNG)

Give variable name as *Path* and paste the two locations delimited by **;** as value to Path variable.

![8]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/8.PNG)

Now, our compiler and runtime environment is all set. Let us check it by repeating the first step and this time we see a different ouput than the previous one.

![8]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/9.PNG)
![10]({{ site.url }}/images/2015-08-28-setting-up-java-ide-with-sublime/10.PNG)

In in next article We will download and set up Sublime Text Editor.







