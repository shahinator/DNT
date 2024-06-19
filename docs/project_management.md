# **Project Management in Summer Semester 2023**

[[_TOC_]]

## **Project background / Introduction**

The purpose of this project is to construct a 3D Digital Twin (simulation) of the square of Nibelungenplatz taking in consideration of the traffic management, emergency response planning, etc. This is an ongoing project and we have to produce the fourth version (.v4) and the scope and milestones will be decided considering the last semesters’ outcome and improvements.

## **Business case / Benefits of doing this project**

Some of the advantages of implementing this project are:

- A detailed visual representation of the Nibelungenplatz square.
- Evaluation of the impact of potential changes
- Understanding the site’s design and functionality
- Identifying potential safety hazards

## **Objectives and scope**

Major Objectives:

- Collecting and preparing data form different resources (city-provided, maps, urban plans, videos recordings etc)
- To create a highly detailed and accurate 3D Digital Twin of Nibelungenplatz including buildings, trees, streets, cars, bicycles, pedestrians etc.
- Visualizing on Dassault 3D platform.
- Improving the video quality without compromising GDPR.

## **Deliverables / Outcomes**

A new version of 3D Digital Twin of Nibelungenplatz square will be created

## **Milestones**

The following milestones have been decided after analyzing the previous semesters’ work

### Milestone 1: Video Recording

- Determine camera positions, camera height, camera angle
- Fix the configuration: frame rate, video length, resolution
- Decide the no of video sets and video duration
- Height should be as high as possible, video should be stable
- camera angle should be perfect.

### Milestone 2: Configure Static Data in Dassault 3D Platform

- Figure out why the city data was not usable and possibly, fix it
- Dassault dashboard using static data (tree, building, camera coordinates)

### Milestone 3: Merge Data of All Cameras

- Understand the code from summer22
- One single data file containing information , i.e. Merge five JSON files after calculating the real world co-ordinates
- Prepare a prototype or model to show the ideas on merging the coordinates
- be able to use the file on Dassault platform

### Milestone 4: Detect Objects (Bike and Pedestrians using YOLO)

- Train YOLO model
- Detect bikes and pedestrians in the videos
- be able to maintain the consistency of the detected object

### Milestone 5: Improve Object Detection Performance

- Extract reference points from video file
- Calculate orientation of moving vehicles
- Improve the orientation calculation
- be able to keep the movement of the vehicles on the Dassault platform smoother

### Milestone 6: Visualize on Dassault Platform

- Configure static data
- Create widget using dynamic data
- Create the digital twin on Dassault platform

## **Team Composition**

### Team Setup

| Group | Members | Focus |
| --- | --- | --- |
| PM | Vyas,Roushan | Setting up project objectives, planning, organizing, task management, resource allocation,Documentation review and controlling the project. |
| Video Recording | Shabu,Mosfiqul,Imran,Shourob,Vyas,Pinku,Fabiola,Izaz | Record Videos |
| Video Trimming/Editing | Fabiola,Izaz | Trim and Synchronize Better quality of Videos |
| Yolo | Shourob,Imran,Pinku | Better quality of data pipeline and dynamic data |
| Dassault-Static | Nidhi,Shikha | Create Static data |
| Dassault-Dynamic | Shobhit,Shabu,Moshfiqul | Creating 3D-Twin from static and dynamic data |

### Managing Roles

| Role | Assigned to |
| --- | --- |
| Project Owner (PO) | Prof. Dr. Karsten Weronek |
| Project Manager (PM) | Vyas,Roushan |
| Project Consultant(PC) | Kien |
| Doc Manager (DM) | Fabiola |
| Gitlab Manager (GM) | Vyas,Roushan |

### Hotseat

- Task: Pick up projector and key for project room - (Responsible**-Pinku Chanda**)
- Where and when?
    - Projector: Building 1/Room 215, during office hour of Frau Rühl
    - Key: BCN-Building/Room 302 at 10:00. If the professor is not there, email or give him a call.

## **Project Duration**

- From 13.04.2023 to 10.08.2023 (14 weeks, breaks excluded)
- Breaks:
    - Exam breaks on 13.07, 20.02, 27.07 (3 weeks)

## **Issue Classification**

- Issues are tasks that need to be done to achieve the project goal.
- Issues are listed in the Gitlab Issue Board.
- Issues are classified based on their labels and workload.

### Labels

| Label | Meaning |
| --- | --- |
| low-level | Minor issues, for use between group members |
| group::pipeline | Issues for the Pipeline-Group |
| group::dassault | Issues for the Dassault-Group |
| stage::to-be-refined | Issues, of which Acceptance Criteria, Priority, and Workload are not yet determined |
| stage::refined | Issues, of which Acceptance Criteria, Priority, and Workload are already determined |
| stage::in-progress | Issues that are currently being handled |
| stage::in-review | Issues awaiting Review and Merge Request Approval |
| priority::low | Issues that should be handled but are not mandatory |
| priority::medium | Issues that do not need to be handled at the moment but must be eventually |
| priority::high | Issues that need to be handled at the moment (no deadline is specified) |
| priority::urgent | Issues that need to be handled immediately (deadline is the following project meeting) |

## **Communication & Contact**

### Internal Communication

| Purpose | Channels |
| --- | --- |
| Internal Meetings | Discord Meeting-Room,  Project Meeting |
| Announcements | Discord announcements,  Project Meeting |
| Person-to-Person (P2P) | Discord general-chat, WhatsApp,  Project Meeting, Google meet |

### External Contact

| Person | Contact |
| --- | --- |
| Daniel Nesic (Dassault) | 3DSwym, mailto:Daniel.NESIC@3ds.com |
| Mahmoud Kanso (Dassault) | 3DSwym, mailto:Mahmoud.KANSO.intern@3ds.com |
| Philipp Winkemann (Data Supplier for static data) | BCN-Building/Room 131, mailto:philipp.winkemann@fb1.fra-uas.de |
| Markus Stummvoll (Facility Management) | mailto:markus.stummvoll@fm.fra-uas.de |

## **Meeting Procedure**

| Step | Duration | Content |
| --- | --- | --- |
| 1 | 15~30 min | Report of each team member about refined, in-progress, and in-review Issues (What was done? What will be done next? Any impediment and need help from someone?) |
| 2 | 15~30 min | Announcements from Prof. and PM |
| 3 | 15~45 min | Refining to-be-refined, pipeline Issues (Only for Pipeline-Group) |
| 4 | 15~45 min | Refining to-be-refined, dassault Issues (Only for Dassault-Group) |
| 5 | Rest of the meeting | Group or P2P Discussion |

## **Terminology**

| Term | Meaning | Synonym |
| --- | --- | --- |
| Static data | Data about the infrastructure of the Nibelungenplatz (e.g. buildings, trees) | Master data |
| Dynamic data | Data about traffic vehicles on the Nibelungenplatz | Moving data |
| Refining Issues | Discussing and determining the Acceptance Criteria, Priority, and Workload of the Issues |  |

## **Sharing Dassault Account**

| Member | Sharing account with |
| --- | --- |
| Vyas | Roushan |
| Nidhi |  |
| Shobhit |  |
| Moshfiqul |  |
| Shabu | Fabiola |
| Shikha |  |
| Imran | Izaz |
| Shourob | Pinku |

## **GitLab**

### Push & Merge Procedure

- By default it is not allowed to push directly into the `master` branch.
- Merge requests can be created from all developers. Merge requests into the `master` branch need to be approved by both Vyas and Roushan.

### Naming Convention

| Naming | Convention |
| --- | --- |
| Commit | See https://www.conventionalcommits.org/en/v1.0.0/ |
| Branch | Either feature_issue_X or fix_issue_X, where X is the ID-Number of the issue you are working on. feature is the default prefix for branch name. Only use fix if you want to patch/fix issues. |
| Folder & File | Lowercase, underscore between words |
| Merge Request | Same as branch name |

## **Milestones Summary**

### Milestone 1 - Video Recording

**Achievements:**

Completed successfully fulfilling all planned acceptance criterias.

### Milestone 2 - Configure Static Data in Dassault 3D Platform

**Achievements:**

Completed successfully fulfilling all planned acceptance criterias.

### Milestone 3 - Merge Data of All Cameras

**Achievements:**

- Successful with different set of models with combined input of cameras.
- Successful with combination of different set of models with combined input of cameras.

### Milestone 4 - Detect Objects (Bikes and Pedestrians using YOLO)

**Achievements:**

- Successfully Trained and Detected the Pedestrian and Bicycles.
- Consistency of detected was also maintained/fulfilled.

### Milestone 5 - Improve Object Detection performance

**Limitations:**
- Tried two approaches one is velocity,second co-ordinate conversion.
- Both were not giving desired results so preferred to stick with previous orientation calculations

### Milestone 6 - Visualize on Dassault Platform

**Achievements:**

- Successfully able to model single camera data with individual vehicles.
- Successfully able to model merged data with individual vehicles.
- Successfully were able to model Bicycles and Pedestrians.

**Limitations:**

- Problems with modeling of multiple vehicles.
- Problems persisted in spite of Outlier Detection and removal,Data cleaning from Yolo side,changing criterias.

## **Improvements and Recommendations**

- Improve the Dassault Widget implementation to support multiple vehicle outputs.
- Host the 3DXC models folder at a specific path for easy addition and updates.
- Documentation about how to build custom 3DXC models.
- Documentation specifying criteria of models that is accepted by Dassault platform.
- No Error/No log messages when uploaded model isn’t reflected can be addressed.
- Implement Pipeline to connect and automate all steps.
- Lighting needs to be taken into consideration in case of recording new set of videos in winter.
- Continue to practise use of Structured and Detailed documentation in a single folder.

