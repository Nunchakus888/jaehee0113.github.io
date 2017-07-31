---
layout: post
title: "Introduction to Git and GitHub"
category: version_control
date: 2016-02-01
comments: true
disqus_identifier: ead791355bd93bd3
highlights: false
---

<pre> <b> {% localize available_in_all_lang %}</b> </pre>

<h1> What is a version control ? </h1>

<p> Simply speaking, as the name suggests, version control is a tool used to control versions of software. </p>

<p> Most software companies use version control to ease the collaboration, bug fixes and deployment. For example, when students write an essay for his or her assignment, normally they would make a draft version of the essay first and through a series of fixes, they would produce the final version of the essay. Likewise, software needs to be fixed or enhanced and keeping the history of changes is very important and version control system (VCS) would help developers to ease the process. </p>

<h1> Creating a repository </h1>

To create the 'first' version of your project, you need to create a repository. You do that by creating a folder and then inside the folder you would:

<pre>
	<code> git init </code>
</pre>

For now, ignore what is happening in that folder.

If a certain folder in your computer is set as a repository, then the VCS will now track every file in that folder and whenever you perform CRUD operations, it will track the changes you made. The repository that is created in your computer can be further classified as your 'local' repository. In reality, there is a remote server where all of your repositories will be stored. If your VCS is Git, then that remote server will be GitHub. In fact, this website is also a repository and all the files are stored on GitHub. Thus, after creating the account, you will be creating the repository on GitHub, and then you will be creating the copy of the repository to your local computer and this is called 'cloning' the repository.

<pre>
	<code> git clone (remote repository address - https or ssh) </code>
</pre>

There you go, you will be seeing a new repository!

<h1> Your 'master' branch </h1>

When you first create the repository, the system will be creating a master branch for you. When you did <code>git init</code>, it should have created the 'master' branch. Like a tree, which always have at least one branch, the repository will always have one branch ready for you. Within one branch, you can start working on your project.

<h1> To record a version, you commit on a branch. </h1>

Now, like writing an essay, you have been coding and would now like to set a version or a point. For example, for any software project, you might have base files. Before adding functionalities, you would want to say, ' I have created these files and would like to record the history with the message " base code created " .' To do this, we make a commit by:

<pre>
	<code> git commit -m "base files created" </code>
</pre> 

Wait! Then the system would say "hey there is nothing to commit!" Well, the system is not wrong. Before making a commit, it is important to understand the concept of staging the file.

<h1> To prevent mistake, stage the changes </h1>

Humans are prone to making mistake. Before making a commit, first you have to stage the changes, to do this

<pre>
	<code> git add [--all] (for specific files then specify it) </code>
</pre> 

To remove (or undo) changes

<pre>
	<code> git rm (something) </code>
</pre> 

And then you will be able to commit files.

<h1> Registering a remote repository (if did <code>git init</code> in your local environment) </h1>

Now, it is safe to update changes to the remote server (in our case, your GitHub account). For example, once you delete the repository folder from your local environment, the commits you have made so far will be gone. Therefore, it is a good idea to synchronize your local repository with the remote repository. To tell to the system that your local repository is equal to a certain remote repository, you will have to:

<pre>
	<code> git remote add [name] [url] </code>
</pre> 

Usually, for the name, developers tend to use 'origin.'


<h1> Push and Pull </h1>

When you are updating your changes made in local environment to the remote repository, you are <b>pushing changes to the remote repository</b>. This will be very simple to understand by now. A beauty of software engineering is that you can collaborate with others. One possible scenario is that one developer makes few commits to your remote repository while you are working on your local repository. Then you want to push the changes to your remote repository. In this case, the system will reject your command because the commit history of your local repository and that of the remote repository are different. In this case, you will need to keep your local repository <b> up-to-date with the remote repository before pushing your changes </b>. In this case, you need to pull new and possibly unknown changes (i.e. commits). Then, you can push your changes to the remote repository.

As you may have realised, these terminologies are coined from the perspective of local repository. Keep this in mind when you are confused with the concepts.


Above concepts are the fundamentals of Git and GitHub and in next series we will go deeper and talk about concepts like rebase and merge.