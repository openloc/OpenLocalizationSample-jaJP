Title: Read me
ms.ContentId: 10FA8CFF-7CA9-42B7-893B-A1BB359ED0D0

# Read me #

Deprecated.

## Environments ##

Currently Open Authoring supports 3 Rendering Environments. MSDN Production, INT and Sandbox. For MSDN Production, we provide 2 states, Live and Stage. Below is the mapping between rendering environments and repository branches.

   | Repository Branch Mapping | Content.VS | Content.ALM | Office365 | AzureGraph | Virtualization |
   |---------------------------|------------|-------------|-----------|------------|----------------| 
   | MSDN (Live) | releases/live (promoted) | releases/live (promoted) | master (promoted) | master (promoted) | master (promoted) |
   | MSDN (Stage) | release/live | releases/live | master | master | master  |
   | INT | master | master | release | release | release |
   | Sandbox | releases/hack | releases/hack | sandbox | *none* | ContainerBits |


## Default Branch Recommendation and Policies ##

Below is the branch policy adopted by Visual Studio team when using Open Authoring, and it's worth sharing.

* **master** 
  - Published to internal integration site so we can see our work integrated in one place before we publish live. 
  - Contains the work we're doing for this sprint and intend to publish next, typically shortly after the sprint ends.
  - In most cases, if you don't need to publish a hotfix, create your topic branch from here.
* **releases/live** 
  - Published to live site. 
  - If you need to publish a hotfix, create your topic branch from here.

Release/User/Feature branches

* **releases/{release}** - content to be released at a point in time. 
  - **releases/M82** - content relevant functionality built during or before Sprint 82. Typically created at the end of Sprint 82. Released concurrent with the product team's M82 deployment, which is typically about a week after Sprint 82 ends. 
* **users/{alias}/{topic}** - an individual's topic branch.
* **features/{feature}** - content that requires independent contributions from multiple authors but should be published together. Not as commonly used as topic and release branches.

### Branch policies

Branch policies can be used to keep quality high and to avoid inadvertent publication of content that is not yet ready. Suggested policy configuration is:

* Block direct pushes to **releases/live**. You must use a **pull request** to update this branch.


## Builds ##

## Repository Structure ##


## Author (How) ##

[!INCLUDE [temp](_shared/markdown-get-started.md)]

[!INCLUDE [temp](_shared/get-tools.md)]

### Create a topic branch

Begin writing with a new topic branch if you don't have one yet. In most cases you create your topic branch from master.

### Create a topic


### Author in Markdown

At the top of your markdown topic, you must add this metatdata (otherwise you'll get build errors):

```
Title: This is my title in long form
Description: This is my description
ms.TocTitle: My short title
ms.ContentId: 00000000-0000-0000-0000-000000000000

```

Set ```ms.ContentId``` to a new GUID. You can get one from Visual Studio: Tools -> Create GUID.

**Tip:** Are you about to copy from another topic and paste into your topic? Are you writing something that you think needs to be used in multiple topics (for example, a common Q&A item)? **You can write it once and use an include!**(#include)

### Structure 

<!--*The best stories also have great structure*-->


#### Folder structure

Use these subfolder conventions to keep our repo experience happy:

 * ```_shared``` - content you intend to share using an include reference. For example ```\library\vs\alm\build\_shared``` contains content that is included in both ```\library\vs\alm\build\index.md``` and ```\library\vs\alm\build\overview.md```.

 * ```_img``` - images used in topics, including screenshots and conceptual art. For example the images used in ```\library\vs\alm\build\vs\define-build.md``` are stored in ```\library\vs\alm\build\vs\_img``` or in ```\library\vs\alm\build\vs\_img\define-build``` if you have a lot of topics in ```\library\vs\alm\build\vs\```.

 * ```_shared\_img``` - shared images. For example, images shared among multiple build topics are stored in ```\Library\vs\alm\Build\_shared\_img```.

#### Q&A sections

Use Q&A sections to share important information that isn't part of the main happy path. Make sure you remember to close them. 
 
	## Q & A
	
	<!-- BEGINSECTION class="md-qanda" -->
	
	#### Q: Should I use Q&A sections?
	
	A: Yes!
	
	<!-- ENDSECTION -->

#### Images

*The image examples in here include blanks after !  and ] because of build issues with code blocks. After that's fixed, we'll correct them.*

To break a line between a step and an image, use a blank line and indent the image with a space character (instead of ending it with a BR tag).

	0. Begin the process.
	
	   ! [Click the begin button] (_img/IC680095.png)

**Tip:** Don't use a tab character to indent the image, or Markdown will treat the image tag as code.

Don't include title text. Do this:

	! [alt-text] (image.png).
	
Without the image title text (so not this):

    ! [alt-text] (image.png "title-text"). 

#### Links to markdown files

*The example link here adds a blank after ] because of a build problem with code blocks.
We'll remove that when it's fixed.*

To link to other markdown files, make sure to include the ".md" extension. E.g.: 

	[Run tests in your build] (run-tests-with-builds-vs.md)

#### Intra-page links

To link to another place in the document:


```html

    [Something great lower in the doc] (#great_stuff)

    blah

    blah

    blah

    <a name="great_stuff"></a>
    ## Great stuff

    awesome
```


#### Include shared content

*The example link here adds a blank after ] because of a build problem with code blocks.
We'll remove that when it's fixed.*

If you want to offer the same blurb of content in two different topics, 
use a content include instead of copying and pasting. 

For example, you 
want to offer the same Q&A item in a few different topics. Put the content in 
a _shared folder and add the include tag in the files where you 
want the show the Q&A item:

    [!INCLUDE[temp] (../_shared/qa-vs-launch-fail.md)]

When you use an include, you must:

 * Include a ms.ContentId GUID metadata variable as described above. You can skip the other metadata items.
 * Specify the relative path to the file (absolute path doesn't work).

You should store shared content in a ```_shared``` sub-folder.

### Commit, publish, push

Ad you write:

* [Commit](https://msdn.microsoft.com/en-us/library/hh967655.aspx#changes) your changes at regular intervals. You don't have to commit every time you save. 
 
* When you are ready, [publish the branch](https://msdn.microsoft.com/en-us/library/jj190809.aspx#publish). 

* As you continue working, you can continue to add to the published branch by [pushing your commits](https://msdn.microsoft.com/en-us/library/hh850436.aspx#push).



## Preview and review

<!--*This is not WYSIWYG exactly, but that's a good thing, and we will keep making it better...*-->

Markdown is a very lightweight format, so it's not too hard read or tweak directly, even in notepad. But for prolonged writing and reading, rendered content is more cognitively efficient.

### Preview your local changes



### Preview your pushed changes

You and your reviewers can preview your changes in the master branch on the OA integration sites.

You can preview your topic branch on OA Sandbox. TBC.


### Use a pull request to review your content

When you are ready for partners and stakeholder to review your content, create a pull request


You and your colleagues discuss the content. You can continue to push changes to the topic branch. When you are ready, complete the pull request, which merges it to the target branch.


**Important - If your pull request is to master or releases/live:**

 * After you merge your pull request, don't delete the source branch until after you have confirmed the build succeeded:
 * If you find errors, fix them, and then create another pull request to merge the fixes.
