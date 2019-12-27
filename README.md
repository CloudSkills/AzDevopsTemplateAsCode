<!--
This is an article template you can use as a quick starting point when writing DigitalOcean tutorials. Once you've reviewed the template, delete the comments and begin writing your outline or article. You'll find some examples of our custom Markdown at the very bottom of the template.



Readers should be able to follow your tutorial from the beginning to the end on a DigitalOcean Droplet. Before submitting your article to the editorial team, please be sure to create a new Droplet and test your article from start to finish on it exactly as written. Cut and paste commands from the article into your terminal to make sure there aren't typos in the commands. If you find yourself executing a command that isn't in the article, incorporate it into the article to make sure the reader gets the exact same results. We will test your article and send it back to you if we run into technical problems, which significantly slows down the publication process.
-->


# How to Use Pipeline Templates to Manage Infrastructure with Terraform on Azure Devops

<!-- Use Title Case for all Titles -->

<!-- Learn about the title, introduction, and Goals sections at https://do.co/style#title-introduction-and-goals -->

<!-- Learn about formatting headers at https://do.co/style#headers -->

### Introduction

<!-- Our articles have a specific structure. Learn more at https://do.co/style/structure -->

Infrastructure as Code is considered a best practice when managing cloud infrastructure. However, it can become hectic if not organized correctly. One way of simplifying Infrastructure as Code for Terraform configurations in Azure Devops is by using pipeline templates to represent our infrastructure. Each value in the template parameters are used to cutomize our configuration which is then built during the build pipeline. This has many benefits:

- No Terraform configuration file drift since configurations are built on the fly.
- Seperate repo permissions for Terraform configurations and live infrastructure code.
- Tracking changes is much more simplified
- Consistency


In this guide, we will use the Azure Devops Demo generator to generate a Project using this method and deploy some resources.

When you're finished, you'll be able to see how this is set up. 

## Prerequisites

<!-- Prerequisites let you leverage existing tutorials so you don't have to repeat installation or setup steps in your tutorial.  Learn more at https://do.co/style#prerequisites -->

Before you begin this guide you'll need the following:

* [Azure Subscription](https://azure.microsoft.com/en-us/)
* [Azure Devops Organization](http://dev.azure.com)


## Step 1 — Setting up environment with demo generator


First, we are going to import an Azure Devops template project into our Azure Devops oranization. This will allow us to get started as quickly as possible. Navigate to the [Azure Devops Demo Generator](https://azuredevopsdemogenerator.azurewebsites.net/) website. 

Sign in with your Azure Devops account. Select **Accept** to authorize the Azure Devops Demo Generator application to access your account. Now we are ready to import our template. Select **Choose Template**:

![ChooseTemplate](\Images\ChooseTemplate.png)

Next, choose the GitHub option in the **Upload your template archive (zip) file from:** box. Paste in the following URL which goes to my GitHub repo that hosts this template:

```https://raw.githubusercontent.com/allanore/AzDevopsYamlAsCode/master/TemplatesAsCode.zip```

Then select **Submit**:

![GitHubTemplate](\Images\GitHubTemplate.png)

 Now, select your organization from the drop down menu and type in a name for the project name. In the example I will be naming the project **TemplateAsCode**. **Check** the box for **The extension(s) are offered to you...** and select **Create Project**:
 
 ![CreateProject](\Images\CreateProject.PNG)
 
  Notice that the **Replace Tokens** and **Terraform** *extensions* are required for this project. Extensions are add-ons for Azure Devops that provide an enhancement to the service. In this case we will be using the Replace Tokens extension to build our Terraform Configuration files during our build pipeline; and the Terraform extension to easily deploy our configurations to Azure. These two extensions will automatically be installed when we import the project.

  Finally, after the import is scuccessful we will get the following message. Select **Navigate to Project** to be directed staight to our new project:

  ![SuccessfulImport](Images\ImportSuccessful.png)

Now we will review the project that we just imported.

## Step 2 — reviewing set up

Another introduction

Your content

Transition to the next step.

## Step 3 — deploying resources

Another introduction

Your content

Transition to the next step.

## Conclusion

In this article you [configured/set up/built/deployed] [something]. Now you can....

<!-- Speak  to reader benefits of this technique or procedure and optionally provide places for further exploration. -->



<!-- Some examples of how to mark up various things

This is _italics_ and this is **bold**.

Only use italics and bold for specific things. Learn more at https://do.co/style#bold-and-italics

This is `inline code`. Use it for referencing package names and commands.

Here's a command someone types in the Terminal:

```command
sudo nano /etc/nginx/sites-available/default
```

Here's a configuration file. The label on the first line lets you clearly state the file that's being shown or modified:

```nginx
[label /etc/nginx/sites-available/default]
server {
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;

    root <^>/usr/share/nginx/html<^>;
    index index.html index.htm;

    server_name localhost;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Here's output from a command:

```
[secondary_label Output]
Could not connect to Redis at 127.0.0.1:6379: Connection refused
```

Learn about formatting commands and terminal output at https://do.co/style#code

Key presses should be written in ALLCAPS with in-line code formatting: `ENTER`.

Use a plus symbol (+) if keys need to be pressed simultaneously: `CTRL+C`.

This is a <^>variable<^>.

This is an `<^>in-line code variable<^>`

Learn more about how to use variables to highlight important items at https://do.co/style#variables

Use `<^>your_server_ip<^>` when referencing the IP of the server.  Use `111.111.111.111` and `222.222.222.222` if you need other IP addresses in examples.

Learn more about host names and domains at https://do.co/style#users-hostnames-and-domains

<$>[note]
**Note:** This is a note.
<$>

<$>[warning]
**Warning:** This is a warning.
<$>

Learn more about notes at https://do.co/style#notes-and-warnings

Screenshots should be in PNG format and hosted on imgur. Embed them in the article using the following format:

![Alt text for screen readers](/path/to/img.png)

Learn more about images at https://do.co/style#images-and-other-assets
-->
