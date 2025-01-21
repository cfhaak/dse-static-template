```
├── build.xml 						= the buildfile used by ant
├── cookiecutter_template.xpr 		= ignore this for now
├── data 							= data directory, containing all your xml files
│   ├── editions 					= files containing the edited documents
│   ├── imprint.xml 				= file with the imprint info for the final website
│   ├── indices 					= indices for persons, places etc.
│   └── meta 						= files concerning the whole website
├── Dockerfile 						= Dockerfile, ignore for now
├── html 							= here the html will be outputted by the xslt
│   └── js 							= java scripts
├── LICENSE 						= the license 
├── nginx.conf 						= server related, can be ignored
├── publish_it.md 					= info about using GitHub-Pages
├── README.md 						= general info about this repo
├── requirements.txt 				= requirements for python*
├── run_it.md 						= info about running the page locally
├── saxon 							= saxon xsl processor
├── tree.md 						= this file
└── xslt 							= contains all xslt-templates
    └── partials 					= contains some xslt-templates that get reused by others
```
\* *use ("python -m pip install -r requirements.txt" to install them if you now, what that means.)*