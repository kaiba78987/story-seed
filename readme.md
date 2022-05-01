# Story seed

Story seed is a seed repository that eases the use of GIT as version control system for writing any kind of story. Some features are only available on Windows.

## Requirements

The following software needs to be installed in order to use the features of the project. The folder bin include some scripts to install them automatically.

- Git
- LibreOffice
- TortoiseGit (optional)
- Microsoft Word (optional)

## How to use?

### Create a new story

1. Clone this repository.
2. Run the shortcuts under bin/ to open a new document that uses a template configured with the main styles used to for writing (you may need to modify the paths used in the shortcuts depending on your Microsoft Office / LibreOffice installation).
3. Save documents as docx or odt.

### Commit your work

We usually need to export our work to pdf to share it with other people. This repository contains a pre-commit script that automates this process and save time.

To enable this feature, copy bin/pre-commit file to the .git/hooks folder of your project. You may modify the script in order to use the installation path for LibreOffice in your device.

Then, all you have to do is commit your document changes. The script will generate the pdf target files and they will be commited too.

### Resolve merge conflicts

Document files are not treated as text files, but binaries instead. In fact, they are composed of XML files and other resources compressed as zip files. So GIT cannot track insertion nor deletions.

Even more, if we create different branches to write some aspects of our stories, we could find that there are merge conflicts. But, again, we cannot resolve them because documents are considered binary files.

Fortunately, if we have Microsoft Word installed and we do this merge action using TortoiseGit, it will use the merging document feature of Word to achieve this conflict resolution. All we need to do is use the control changes features of Word and save the file. Then we will mark the conflict as resolved, commit the changes and that's all!

If we cannot use Windows or we don't have a license of Microsoft Office, then we can workaround the problem. Simply, use a text based format to save your documents, as rtf. Some document features will be lost.
