# Manage Project Access

While workspace roles define workspace-wide access, not all projects need to be accessible/editable by everybody in the workspace. 

Visibility and permission settings within projects allow granular control over who can do what. 

## Project Visibility

Project visibility determines who can view projects within or outside the workspace. 

**Private**: Only members with direct access can view/edit the projects.

**Internal**: Anybody within the workspace can view the published branches of the project except guests. Guests need direct access to the project. Makers within the workspace can edit these projects.

**Public**: Everyone including anonymous visitors can access the project. Makers within the workspace can edit these projects.

> **Note:** Makers would require access to the git repository to edit Git projects.

### Change Project Visibility

To update the project visibility or add users to a project, click on the **Share** button (next to **Edit in Studio**). From here, you will be able to modify the visibility settings of a project

![](../assets/images/manage-project-access.png)

> Keep in mind that users will see different projects depending on the following criteria:
> - Their permissions in the **workspace**, or
> - Their role in the **project**, or
> - The **visibility settings** of the project (private, public, or internal)


## Project Roles

Project roles determine who can edit projects and their settings. These roles include:

![Project Roles](../assets/images/project-roles.png)

**Viewer**: Viewers can view documentation and consume mock servers **including unpublished branches**.

**Editor**: Editors in addition to viewer access, can edit private projects. They can also view project settings and automation logs. To edit these settings, members require admin access. Internal/public projects can be edited by makers across the workspace. 

**Admin**: Admins in addition to editor access can update visibility, manage branches, add members and delete the project. 

> Project creators start as the only admin when a project is created. *Everybody else including workspace owners/admins would require the project admin to add them explicitly in the project to manage settings and/or view unpublished branches*.

### Grant Project Permissions

To add users to a project, click on the **Share** button (next to **Edit in Studio**). From here, you will be able to add members with appropriate roles to the project

![Direct Access](../assets/images/direct-access.png)