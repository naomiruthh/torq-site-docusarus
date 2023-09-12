When you create a workflow on the designer, a YAML file is created with all the workflow information. To import and export workflows, you'll use this YAML file.

[Import](/v1/docs/import-and-export-workflows#import-a-workflow) and [export](/v1/docs/import-and-export-workflows#export-a-workflow) enable you to share a workflow between accounts or to edit the workflow directly in the YAML file.

Export a workflow
-----------------

There are two ways to export a workflow.

### Workflows page

1.  Go to the **Workflows** page.
2.  Click the menu icon for the workflow to export.
3.  Click **Export**.

![](https://cdn.document360.io/e159bc51-b5b1-4b1f-af39-a9db2fa968d6/Images/Documentation/image-1671091675531.png)

### Designer

1.  Open the workflow in the designer.
2.  Click the menu icon at the top right part of the page.
3.  Click **Export**.

![Export a workflow from the designer](https://cdn.document360.io/e159bc51-b5b1-4b1f-af39-a9db2fa968d6/Images/Documentation/image-1671091887819.png)

Import a workflow
-----------------

To import a workflow, go to the **Workflows** page, click **Import**, and select the workflow YAML file.

When you import a workflow that includes nested workflows, Torq checks and does not duplicate the [nested workflows](/v1/docs/create-a-nested-workflow) that already exist in the account to which you're importing. 

![Import a workflow](https://cdn.document360.io/e159bc51-b5b1-4b1f-af39-a9db2fa968d6/Images/Documentation/image-1671092244652.png)

  

Handle failures
---------------

Below are a few tips to help you deal with import and export failures. Keep in mind that imports and exports may also fail due to momentary issues.

### Workflow export

An export failure might be an indication of a problem with the workflow you're trying to export. Try running the workflow by clicking **Run Workflow** or **Test Run** (depending on whether your workflow is published or in the draft state) and fix any errors you encounter. When the workflow run completes successfully, retry the export.

### Workflow import

An import failure might indicate that the YAML is not valid. If the workflow was exported, the YAML was valid. If the import is failing, most likely a manual change was made to the YAML file, which broke it. These are some common reasons a YAML might be broken.

*   A nested workflow points back to one of its ancestors. For example, if **Workflow** **B**  is nested in **Workflow A**, then **Workflow A** can't be nested in **Workflow** **B**.
*   The workflow YAML file points to a nested workflow that doesn't exist on the account to which you're importing.

If no manual changes were intended, you can revert the YAML to a previous version that doesn’t contain manual changes or, if possible, try exporting the workflow again.