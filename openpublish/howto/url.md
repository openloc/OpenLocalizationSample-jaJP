Title: URL
ms.ContentId: A0F618B9-4473-48C1-BD20-A710AD5142C1


##URL Structure
Each topic (markdown file in Git repo) has to be rendered in each environment all the way through live site. In order to scale with large combination of product, repository, and branches, a standard URL namespace schema is developed as below 

    http://{site}/{locale}/[{areaPath}]/[{product}]/[{version}]/{contentPath} 

| Parameter | Required | Source | Description |
| --------- | -------- | ------ | ----------- |
| Site | Required | Publishing metadata provided at account provisioning | The URLs to the host name of the Web app that renders the content. It can be the URL for public site, internal testing or staging environment, or even localhost of local preview. |
| Locale | Required | Document metadata from metadata file in Git | A string in {language}-{territory} format to indicate the locale of the content. The existing MTPS locale fallback rule also applies here.  |
| AreaPath | Required | Publishing metadata provided at account provisioning | A partitioning scheme for content. It works like the MTPS iRoot today to determine which UX Theme will be applied to the content. The same content rendered under different AreaPath will look very differently |
| Product | Required | Document metadata from metadata file in Git | A string that describes the product for which the content is written |
| Version | Optional | Document metadata from metadata file in Git | Al SEO friendly version string that contains a human friendly product name and a version |
| Content Path | Optional | Inferred from VSO Git repo file path, or defined in publishing metadata file | A path structure for a content item that authors their content. By default, this path structure is the folder path of a content item in a repo. It can be overridden in the repository metadata files by content author or site manager |

With this URL schema defined, content author and site management are given great flexibility in the layout of the content files in repo as well as rendering URLs.  

- Knowing content author and site manager always like to have the flexibility to define content URL for many reasons, this URL schema design offers the ability to override the default URL structure through projectionURL metadata, which can be updated either through publishing management portal or metadata files in repo. With the exception of locale element that must follow the site, every other components in the URL structure is optional and can be overridden. For example, an auto-generated default rendering URL for VSO Git pushes.md should be ** http://www.visualstudio.com/en-us/integration/vso/rest/apis/git/pushes **, but site manager doesn’t like this URL structure for some reason, he can override it in metadata to something like ** http://www.visualstudio.com/en-us/integrate/reference/reference-vso-git-pushes-vsi **(this is actually the URL used for TechEd release).  
- This URL schema design does not require the layout of the repo in any particular manner. Although it is expected that a repo contains content for a single locale, this design does not require it as long as locale metadata is added properly for each content file (individually or in bulk). For design details of URL namespace schema, go to Open Authoring URL schema Design 
