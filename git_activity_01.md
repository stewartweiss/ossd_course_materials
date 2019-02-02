# A Git "Hands-on" Activity

Copyright (c) 2019 Stewart Weiss

The above author acknowledges that this work is a derivative of an activity
developed by Dr. Joanna Klukowska of the Courant Institute, licensed by her
under a [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.


## Introduction

This activity models the situation in which a group of people are collaborating 
on a project that they themselves created, not one created by some external 
organization. This is the case, for example, when they have decided to build 
some new application together, or have been given a team assignment within some
organization.

This type of scenario is a simpler one to understand than one in which the team 
is collaborating on a contribution to an external project, mostly because in this
situation, there is a single shared repository for the project, to which each team
member has write-permission, rather than an external repository to which they each have
only read-permission and to which they can only issue *pull-requests* when they want to 
incorporate their changes. Therefore, it is a good first exercise in learning how to
use git.

The standard *workflow* in this scenario is that each team member *clones* the shared
repository to her local machine and works within that cloned repository, making
changes through git's set of commands.

Therefore, in this activity, you will collaborate with two or three other people,
each working on the same repository.
As different team-members try to make changes to the content of the shared repository,
the team may  encounter some technical issues. The objective of this activity 
is to learn how to resolve different types of issues
that may arise when collaborating with other people on a shared repository. The 
lessons learned in this exercise will extend to the more complex case of working
on an external repository not maintained by the team.

## Conversion of English Language Instructions to Git Instructions 

In the section below named **Detailed Instructions**, the instructions are written 
in ordinary English. These  instructions correspond to sequences of one or more 
`git` commands as follows.

- If an instruction  states "create a file, and stage and commit it", 
this means that you should create the file by whatever means is described, then
add it to the staging area and commit it using a descriptive message. If 
`FILE_NAME` is the name of the file, then you type

  ```
  git add FILE_NAME
  git commit -m "MESSAGE FOR THE COMMIT"
  ```
- If an instruction  states "push the changes to the remote repository", 
you should make sure that all of the current changes are committed (see above) 
and then push those changes using the command

  ```
  git push origin master
  ```

- If you run into any problems while completing the sequence of instructions in 
this activity, raise your hand and someone will try to help out as quickly as
possible.

### Detailed Instructions

The instructions are in the table below. Each row of the table is called a "round".
The rounds should be performed in the order they are listed. The columns correspond to 
what the specific team members should do in that round. There are four columns, 
one for each team member. To be clear, as an example, the third column, second row
is what team member 2 does in the second round.

If a row extends across all columns, it means all team members perform that instruction
in that round.

<table>
<tr> <th>Round#</th><th> Member 1</th><th>  Member 2</th><th>  Member 3 </th><th>  Member 4 </th> </tr>

<tr>
</tr>

<tr>
<td>1 </td>
<td colspan=4>  

Clone the team repository to the local machine using the instruction

`git clone REPO_URL`

</td>
</tr>
<tr>
<td>2 </td>
<td >

Create a `README.md` file, which should contain a top level heading with a team name. 
Stage and commit the file and push the changes to the remote repository.  

</td>
<td>

Create a `LICENSE.txt` file, selecting one of the available software licenses.
You can find license text  at [choosealicense.com](https://choosealicense.com/).
Stage and commit the file and push the changes to the remote repository. 

</td>
<td>

Find an image file that can be copied, using [Wikimedia Commons](https://commons.wikimedia.org/),
to serve as an avatar, icon, or mascot for your team. Download the file into the
local repository,  and stage and commit the file. Save the URL of the file
because you will need that information later. Push the changes to the remote repository.

</td>
<td> 

Visit a legal, free music download site, such as [Free Music Archive.org](https://freemusicarchive.org/about/)
and download an `mp3` file. Download the file into the
local repository,  and stage and commit the file. Save the URL of the file
because you will need that information later. Push the changes to the remote repository.
</td>
</tr>
<tr>
<td>3 </td>
<td colspan=4>

- Create a new empty Markdown file named with your own name and the ".md" extension. 
- Add the file to the repository, commit and push changes to the remote repository,

</td>
</tr>
<tr>

<td colspan=5>

In the previous two steps, most of you should have encountered some issues when you 
tried pushing the file to the remote repository.
Since several people push changes to the same repository, most of you tried to 
push after someone else modified that remote repository. In many cases Git can figure out how to combine
the changes made by different people. However, your local copy of the repository will
no longer be a current copy of it and will need to be updated.
This is the purpose of the `git pull` command.  You will need to execute 

`git pull` 

to update  your local copy of the repository with the latest version of the remote 
repository. That is the next step.

</td>
</tr>

<tr>
<td colspan=5 align=center>

__Resolving merge conflicts__

</td>
</tr>

<tr>
<td>4 </td>
<td colspan=4 >

- Run `git pull` to synchronize your local repository with the remote one.
- In your local repository you should now have the file named `README.md`.
- Edit the `README.md` file by adding your name to the file right below the name of the
team.
- Stage and commit the changes and push them to the remote repository.  
</td>
</tr>

<tr>
<td colspan=5>

At this point, multiple users modified the same lines of the same file. Git can no
longer resolve these changes on its own. The problem needs to be resolved by a
person, not Git. This is an example of a  __merge conflict__. 
To resolve it, the user has to edit the file manually and decide which of the 
changes should be merged and which should be removed.

As you are resolving the merge conflicts manually, make sure that all of your
team-mates names end up being listed in the `README.md` file exactly once.

</td>
</tr>

<tr>
<td colspan=5 align=center>

__Managing forks and remotes__

</td>
</tr>


<tr>
<td>5 </td>
<td colspan=4>

- Go to the team's original repository on GitHub and use the `fork` button to
fork the team's repository to your own account. 

- Add your own fork of the repository as a `remote` for your local repository. To do
this,  in your repository on your local machine, run the command

    `git remote add myfork URL_TO_THE_FORK`

    where `URL_TO_THE_FORM` is replaced by the actual URL

- Run the command

    `git remote -v`

    and record the results in the body of your file (the one with your name in it).

- Stage and commit the changes to the file that you just edited  and push them to 
the `myfork` remote using the command

    `git push myfork master`

- Look at the files stored in the original repository in the course organization and in
your private fork; they should be different. Why?  What should have been done to
prevent this from happening, and what can be done at this point?

</td>

</tr>







<tr>
<td> </td>
<td>

</td>
<td>

</td>
<td>

</td>
<td>

</td>

</tr>




<tr>
<td> </td>
<td colspan=4>

</td>

</tr>


</table>
