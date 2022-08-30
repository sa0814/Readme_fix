![alt text](https://raw.githubusercontent.com/emeyers/Brain-Observatory-Toolbox/backend/BOTDataSchematic.png) 

Brain Observatory Toolbox
A MATLAB toolbox for accessing and using the neural recording public datasets from the Allen Brain Observatory[1].

👀 See the Brain Observatory Toolbox in action, with the EphysDemo and the OphysDemo demonstration live scripts.

🚧 The Brain Observatory Toolbox is at an early stage (v0.9), meaning two things:

Questions, suggestions, and other feedback are highly welcomed (in the Discussion forum)
Some interface compatibility changes may occur at each early-stage release (v0.9.x)
The Allen Brain Observatory dataset records, files, and values browsed and accessed by this toolbox would not be impacted.
About the Allen Brain Observatory datasets
Data releases from the Allen Brain Observatory include two datasets of neural activity recordings:

Dataset	Recording Type	Nickname	Details
Visual Coding Neuropixels [2]	Large-scale neural probe recordings	"ephys" (electrophysiology)	details
Visual Coding 2P [3]	Two-photon calcium imaging	"ophys" (optical physiology)	details
The Visual Coding datasets are both collected from the living mouse brain during presentation of varying visual stimuli. Technical white papers (see Details for each dataset) provide detailed information about the experimental technicalities and computational pipelines.

About the Brain Observatory Toolbox (BOT)
The Brain Observatory Toolbox (BOT) provides a uniform interface to access and use these Visual Coding neural datasets.

The BOT interface provides tabular representations of available dataset items and object representations of specific dataset items:

alt text

Key Points:

Dataset items supported include experimental sessions (for both 2P and Neuropixels) as well as probes, channels, and units (for Neuropixels)
Tabular indexing or unique item identifiers allow specific item selection from item tables, for inspection and analysis as item objects
Item object properties access direct, derived, and file-linked values for an item
"On demand" properties defer value retrieval, for those item object properties involving extensive compute or file reading
Item object methods are used to compute values requiring additional user-specified arguments
Local caching is implemented*, to provide the fastest possible initial and repeat performance within and across MATLAB sessions
*For retrieved item information, object representations, and file contents

Installation Instructions
Download the .zip file from the latest GitHub release
Unzip via preferred system tool to desired local folder location
Open MATLAB
Add root directory of the unzipped folder contents to the MATLAB path, in one of three ways:
Navigate to root directory in the Current Folder browser and select "Add to Path" from the right-click context menu, using the "Selected Folder" option*
Open the Set Path dialog from the Environment section of the Home tab
Call addpath(<root directory location>) in the Command Window
*The BOT is contained in the +bot package folder. For package folders, adding the parent folder is sufficient to include all package contents.

Required products
MATLAB (R2021a)
Image Processing Toolbox (if running the Visual Coding 2P demonstration OphysDemo.mlx)
Getting started
Four MATLAB live scripts are provided to help get started:

Live Script(s)	About
EphysDemo.mlx
OphysDemo.mlx	Demonstrations of illustrative neurophysiological analyses using the BOT and the datasets
EphysTutorial.mlx
OphysTutorial.mlx	Step-by-step instruction and "under the hood" technical detail about using the BOT and the datasets
Or to get a fast first look yourself, enter the following commands in MATLAB:

>> sessions = bot.fetchSessions('ephys'); 
>> head(sessions) 
>> session = bot.session(sessions(1,:))
>> methods(session) 
References
[1] Copyright 2016 Allen Institute for Brain Science. Allen Brain Observatory. Available from: portal.brain-map.org/explore/circuits.

[2] Copyright 2019 Allen Institute for Brain Science. Visual Coding Neuropixels Dataset. Available from: portal.brain-map.org/explore/circuits/visual-coding-neuropixels.

[3] Copyright 2016 Allen Institute for Brain Science. Visual Coding 2P Dataset. Available from: portal.brain-map.org/explore/circuits/visual-coding-2p.

Acknowledgements
Initial engineering work was supported by the Foundation of Psychocultural Research and Sherman Fairchild Award at Hampshire College and hosted by the Center for Brains, Minds, and Machines at the Massachusetts Institute of Technology.

Cite As
Ethan Meyers (2022). Brain-Observatory-Toolbox (https://github.com/emeyers/Brain-Observatory-Toolbox/releases/tag/v0.9.1), GitHub. Retrieved August 30, 2022.

