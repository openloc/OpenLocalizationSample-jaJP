Title: TOC
ms.ContentId: FDEAC7A6-0B8A-4091-951D-1E211A88EFE8

## Table of Content (TOC)
TOC is authored in markdown format as a separate file at the root of the content folder where the content author needs to have TOC structure captured. 

- TOC.csv
```
*       
**      
***     
***     
**      
***     
```

-ContainerNodeTitles.csv

```
*       
**      
***     
***     
**      
***     
```

The TOC file constructs as the following convention:

1. The file name should be TOC.csv
2. Asterisks in the first column is the standard markdown format for list, it is used there to indicate at which level (relative to toc.csv file) the content should show in TOC. There is no limit to the depth of levels in the TOC file, however we do limit it from rendering to 4 levels.
3. Content type is the 2nd column to uniquely identify content file even if it is at a different repo or file location. If a specific product version is referred to, product id and version id should also be specified after content id 
4. The 3rd column will provide the 


### External Link
### Container Node

## Global TOC

Global TOC is used in Three Column Template to build the breadcrumb navigation cross different centers.

- GlobalTOC.csv:

````
*,oa-toc-external:msdn,https://msdn.microsoft.com
**,oa-toc-external:alm,https://msdn.microsoft.com/en-us/library/fda2bad5(v=vs.140)
***,oa-toc-external:test,https://regex101.com
***,oa-toc-center:tfs,/Library/vs/alm/TFS
***,oa-toc-center:build,/Library/vs/alm/Build
***,oa-toc-center:code,/Library/vs/alm/Code
***,oa-toc-center:work,/Library/vs/alm/work
````

- GlobalTOCTitle.csv:

````
msdn,MSDN
alm,ALM
test,Test
tfs,TFS
build,Build
code,Code
work,Work
````
The center should be same with siteCatalog.json


