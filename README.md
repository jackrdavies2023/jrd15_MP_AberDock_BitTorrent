# jrd15 MP AberDock BitTorrent Tracker Website
This is the main repository for the AberDock BitTorrent Tracker Website. This repository aims to provide documentation of the project and links to the source repository as a submodule under /src.

## What is AberDock?
AberDock is a website designed to promote the sharing of content via the BitTorrent protocol. It does this by implementing a statistics system where users can compete to be in the Top 10 ranks. Users are ranked based on their share ratio. The bigger the ratio, the higher the rank! The share ratio is calculated by `upload / download`. The more a user seeds (uploads), the higher their ratio increases.

The site implements a fully functional search engine and upload system, making it easy for users to find the content they are looking for as well as submit their own.

A torrent v1 compliant announcement/trackig system is also implemented, allowing the site to communicate with popular torrent clients such as Deluge. 

## File structure
Below is a list of directories and files, accompanied by their description.

 - /src - The main source code of the project. Further information on how to configure and deploy an instance of AberDock can be found in /src/README.md.

 - /docs - A directory containing documentation of the project, such as weekly diary, project outline, mockup slides of user interface and diagrams explaining the database structure and back-end classes.

     - /docs/diagrams - A directory consisting of UML diagrams for the SQL database and back-end classes. Created using [draw.io](https://draw.io)

     - /docs/diary - A directory containing my weekly diary, which documents the development process of AberDock. 

         - /docs/diary/images - Images referenced in the weekly diary.

         - /docs/diary/jrd15_mp_diary.md - The markdown document consisting of the diary.

     - /docs/outline/MMP_OutlineProjectSpecification_jrd15.docx - Initial project outline specification.

     - /docs/ui - A directory containing presentation slides of the initial UI mockup.

         - /docs/ui/MMP_AberDock_LayoutMock.pptx - A powerpoint document containing slides used to mockup the initial design goals.

         - /docs/ui/img - A directory containing screenshots of the powerpoint slides.
