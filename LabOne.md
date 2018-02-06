# First Lab: Setup

## Git
Git is a distributed version control system designed to facilitate modern, multi-party development.
Perhaps the most important feature of Git is that it allows developers to keep track of changes in 
their code, to develop different features, to create projects that build on other work, and to be
able to track and undo any steps along the way. 

Because it is *distributed*, Git facilitates development by one or more people at one or more places.
Local version control is maintained separately in each place, and can be synchronised to a remote
repository as needed. While Git is a very popular approach to source control, it can be a difficult
technology to learn, both from a theoretical perspective, and due to the sometimes-counterintuitive
commands.

If you've not used Git before, please follow the tutorial below: 
<https://try.github.io/levels/1/challenges/1>

An introductory tutorial to GitLab (the "protected" version of github) will be delivered as part of the first Lab.







## Getting Started

### Ensure that you have git installed

All of the Linux machines in the School of Computing labs already have git installed.

If you're using your own workstation, then there are instructions for Linux, Windows and Mac [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

If git is installed correctly, then this command-line command:

```Shell
git --version
```

should produce a sensible message indicating what version of git you have installed.  Any reasonably recent version of git should do.

### Create a new project

1. On this web site (and after logging in), go to your [home page](https://gitlab.com/) and click the *New Project* button at the top right of the page.
2. Enter a name for your new project.  It's usually best to choose a project name using just lower-case letters and hyphens (and no spaces).
3. Enter a description for your project.  This is optional, but you should nevertheless do this.
4. Click *Create project*.

### Clone your project

After clicking *Create project*, you're taken to your new project's home page.  At the top you'll see something like the following:

<p>
<img  align="middle" src="/uploads/aaf380801058c8269c7fe4a7dd3a248e/snapshot.png"/>
</p>

The text `https://gitlab.com/mj2018/test.git` is the address of your GitLab repo; the address of your own repo will of course be different to the one shown here.

On the left, you can specify one of two protocols: SSH or HTTPS.  Unless you *know* that you have SSH configured, you should select HTTPS.

The next step is to make a working copy of your repo on your own workstation.  This is known as *cloning* your repo.
Use the following git command to clone your repo (replacing the git address with that of your own repo):

```Shell
git clone https://turing.computing.dcu.ie/sblott/test.git
```

You will be asked for your School of Computing user name and password.
Your project will be copied into a new directory in your current working directory.

`cd` into that directory (for example, `cd test`).  Of course, for the moment your new project is still empty.

### Tell git who you are

Tweak the following to meet your needs:

```Shell
git config user.name "Musfira Jilani"
git config user.email "musfira.jilani.engg@gmail.com"
git config credential.helper store
```

Important: *use your  email address*.

### Create a file

Using a text editor, create a file named `README.md` with the following (or similar content):

```Markdown
## My Project

Welcome to my project, I hope you enjoy it.
```

This is a [markdown](https://daringfireball.net/projects/markdown/) document
(hence the `.md` suffix).  Markdown is a readable text mark up language which
is easily convertible to HTML.

Tell git to track your new file (otherwise, git will just ignore it):

```Shell
git add README.md
```

Commit your changes (and give them a suitable commit message):
```Shell
git commit -a -m "Add README file."
```

And push your changes to GitLab:

```Shell
git push
```

Now, when you visit the page for your new project on GitLab, you will see your new file (and it's contents).

### And continue...

Whenever you add a new file which you want git to track:
```Shell
git add some_file.py
```

Whenever you want to commit your changes:
```Shell
git commit -a -m "Some commit message."
```

Whenever you want to push your changes to GitLab:
```Shell
git push
```

And, if this is a team project, whenever you want to pull changes made by team mates:
```Shell
git pull
```

### Tracked files and staged changes

One aspect of git which new users often find confusing is tracked files, staged changes and committed changes.

Git only stores *tracked files*.  It ignores other files.
For example, in a Java project you would have files `Main.java` and
`Main.class`.  We would want to track changes to the `.java` file but ignore the
`.class` file (because it can easily be recreated by compiling the `.java` file).

We tell git which files we want to track with:
```Shell
git add Main.java
```

You only need to do this once.

When committing changes, git requires that changes are first *staged* and then *committed*.  This can be confusing.

The simplest way to avoid this confusion is to **always** stage and commit files at the same time; that's what the `-a` flag does below:
```Shell
git commit -a -m "Some message."
```

So, ... a tip: *always use `git commit -a`*.

### Other useful stuff

Find out the status of the files in your repo:
```Shell
git status
```



List all commits:
```Shell
git log
```

There's a useful utility for Linux and Mac called `tig`; see [here](https://github.com/jonas/tig).




































## Amazon AWS

Amazon AWS is a cloud stack that provides compute, storage, database, and other functionality from a centralised console.
The Web Services provided are based on a pay-per-use model, with different criteria depending on the service. 

AWS has a free trial tier, please sign up for it:
<http://aws.amazon.com/>

## Send your details

Please email your gitlab username and amazon AWS username to [musfira.jilani@dcu.ie](mailto:musfira.jilani@dcu.ie)

## Bonus: Set up Hadoop

Download Hadoop and run the example single-cluster grep application.
<https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/SingleCluster.html>

You might need to install oracle java, or to ensure that the ports are listening correctly.
