# DraftingAssistanceTracker
Andrew Lee's ongoing projects to automate repeated construction drafting and markup processes.
All done on my own time. Mostly a passion project for me, I like automating things


PROJECT 1: Hand drawn MH diagram to Microstation drawing
* End goal: Automatically turns hand drawn Manhole diagrams into (1) Bluebeam drawing created with native markups and (2) Microstation ready drawings, with layers. Separates different ckts by color and labels. End product will come with a built in GUI and quick review loop to verify 
* Status: 10%
* Done: Created machine friendly MH diagram template. Identified scan requirements (24 bit RGB TIFF @ 300DPI), test scan via Windows Image Acquisition, high level color separation and template subtraction. Achieved <1 pixel page alignment with April Tags and checkerboard edges. Identified high level requirements for export to microstation.
* TODO: Awaiting delivery of DS-50000 large format scanner for further development. Must decide on an internal "universal" on-page coordinate system, and how to convert that to .bax + .DWG. MUST CREATE A MICROSTATION EXPORT PLAN.


PROJECT 2: Ocalc to Bluebeam Stickfigure
* Purpose: Automatically turns Ocalc poles into Bluebeam native stickfigures, automatically formatted and measured out. Removes repetitive hand drawn work.
* Status: 60%.
* Done: Bluebeam .bax format documentation; .bax generator; relevant information extraction via pplx_extract; initially generated stick figures; adding and switching output "templates" in isolated folders; adding additional geometry (termimesh, guys).
* TODO: Replace drawn measurement labels with Bluebeam native measurements; Add customizable "templates" added to output .bax files; Add text box collision detection and prevention; Auto insert "suggested HECO standards" per pole, based on higher level pole properties (components, # of phases, span attachments and angle, **EXISTING VS NEW DETECTION**). 


PROJECT 3: pplx_extract
* Purpose: A general info extraction library for Ocalc pplx and pplld files. Extracts pole shape and components to a typed object model, and schema agnostic normalized tree.
* Status: Complete.
* Roadmap: N/A
