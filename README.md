# Project Structure Documentation

## Overview
This document outlines the file structure and management approach for our video editing projects using Kdenlive. The aim is to ensure consistency, ease of access, and efficient collaboration across the team.

## Directory Structure
Our project consists of two main components: the Git repository for project files and a local "Media" folder for all media assets.

### Git Repository
Located on GitHub, this repository contains only the Kdenlive project files (.kdenlive). These files include editing information but do not contain actual media files like videos or audios.

**Path**: `https://github.com/[username]/[repository]`

### Local Media Folder
This folder is stored locally on each collaborator's computer and contains all the media files used in the projects.

**Structure**:
```shell
Media/
│
├── RawMedia/
│ ├── Video/
│ ├── Audio/
│ └── Images/
│
├── Assets/
│ ├── Video/
│ ├── Audio/
│ └── Images/
│
└── Exports/
```

- **Raw Media**: Unprocessed media files, directly from cameras or other sources.
- **Assets**: Processed and ready-to-use media files, categorized by type.
- **Exports**: Final versions of edited videos.

### To create that structure
```
mkdir -p ./Media/Assets/Audio
mkdir -p ./Media/Assets/Images
mkdir -p ./Media/Assets/Video
mkdir -p ./Media/RawMedia/Audio
mkdir -p ./Media/RawMedia/Images
mkdir -p ./Media/RawMedia/Video
```

## Symbolic Links in Projects
Within each Kdenlive project, symbolic links (symlinks) point to the corresponding folders in the local "Media" directory. This allows the project files to access the necessary media without storing them in the Git repository.

## Remote Access (Optional)
For shared access, the "Media" folder can be hosted on an FTP server or another cloud storage solution. Adjust the symbolic links in each project to point to this shared location.

## Workflow
1. **Setting Up**: Clone the Git repository and set up the "Media" folder on your local system.
2. **Working on Projects**: Use Kdenlive to edit projects. Media files should be accessed through the symbolic links in the project.
3. **Saving Work**: Commit changes to the `.kdenlive` files in the Git repository. Do not commit large media files to Git.
4. **Exporting Final Videos**: Place the final, rendered videos in the "Exports" folder.

## Best Practices
- Always keep your local "Media" folder organized as per the structure.
- Regularly back up your "Media" folder.
- Do not modify media files directly in the "Raw Media" folder; copy them to the "Assets" folder first.

```shell
ln -s /home/nox/Media /home/nox/Videos/Media
```

