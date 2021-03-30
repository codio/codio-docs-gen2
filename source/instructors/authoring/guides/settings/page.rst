.. meta::
   :description: Page Settings

## Page
### Layout
You can choose from a variety of panel layouts for each page of content.

![authtoken](/img/guides/layouts.png)

The layouts we currently offer can be found in the dropdown list.

[Click here](/courses/settings-actions/#specifying-the-panel-number) for information on how to reference these panels when auto opening code files, url previews or terminal windows.

The top-most and default entry in the Layout dropdown is **Previous**. This means it will use the same panel layout as specified on the previous page.

<a name="show-hide"></a>

### Show/Hide Folders
Your content will often want to show code samples. Codio's recommended approach is to put each set of code samples into a dedicated folder. Then, using the page settings, you can specify that folder. All non-specified folders are hidden from view in the file tree.

The benefit of hiding folders is that the student is not distracted by a large list of folders and files that are not relevant to the topic your are explaining.

### Full File Tree:
![authtoken](/img/guides/project_1.png)

### Hiding of Folders:
![authtoken](/img/guides/project_2.png)

###  Defining folders
To define which folders to show make sure your page is selected. Next, in the **Show Folders** field, specify the folder or folders which should be shown in the file tree. Use the `;` character to separate multiple folders.

![authtoken](/img/guides/project_3.png)

If you have several pages that show the same folders, you only need define the folders on the first page of the set of pages. All subsequent pages will use the same **Show Folders** setting until a new one is encountered.

### Content Type
You can specify whether the page content type is markdown (strongly recommended) or HTML. If you choose HTML, then you will need to set the page HTML header and footer in [Global Settings](/courses/settings-actions/#global).

<a name="teacheronly"></a>
### Teacher only content
If this switch is enabled then the page contents will not be show to students. Teachers will be able to see it when they open an assignment in a course or when opening a students assignment.

### Learning Objectives
This is a tag field that can be useful for data analysis.

