Title: FileInclude
ms.ContentId: 0A8159AD-C7CE-4C94-8B7A-9190E8C8B8C0
ms.TocTitle: File Include
ms.topic: File Include


# File Include

A markdown file can reference other files inside its content, such as images, code snippets, and another markdown file that is shared across multiple topics.

The following items are needed for a file include:

- Required: Folder path within the repo


- Optional: Repository Id, which includes: account name, collection name, project name, repository name. The repository of the file is used if it is not specified.

The format of a file include is

    [{accountName}\{collectionName}\{projectName}\{repositoryName}:{folderPath}]

An example is 

	![Introduction](..\images\Introduction.png)
