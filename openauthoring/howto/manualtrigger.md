Title: Promotion Tool
ms.ContentId: E15886C3-251F-41DD-8744-92F7725F716D

# Manual Trigger to Promote Content

## Download

Download the content promote tool from: [\\msdnfs\CodeDrop\Drops\PromotionTool](\\msdnfs\CodeDrop\Drops\PromotionTool "\\msdnfs\CodeDrop\Drops\PromotionTool")

## Usage

```
Usage: PromoteContent.exe <environmentName> <accountName> <collectionName> <projectName> <repositoryName> <branchName>

Promotes content from Stage to Live for a given environment
arguments:
environmentName:   Name of the environment in which to promote content. This is prod for live.
accountName:       Name of the VSO account that houses the content repository. This is always MsEng
collectionName:    Name of the collection that contains the project. This is always DefaultCollection.
projectName:       Name of the project under the VSO account that contains the content repository. This is always Documentation.
repositoryName:    Name of the repository that contains the content Ex: VSContent, O365 Content, AnalogContent
branchName:        Name of the branch in the repository that contains the state of content. This is always Master.
--------------------------------------------------------------------------------
Example: 
PromoteContent.exe prod MsEng DefaultCollection Documentation O365API master

```