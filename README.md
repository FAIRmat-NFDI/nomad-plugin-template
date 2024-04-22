# nomad-plugin-template
A template repository for creating a repository with a NOMAD plugin package.

> [!WARNING]
> The template is not yet ready for production usage.


## Getting started

1. Click on the `Use this template` button and create a new plugin repository. The form will ask you to fill out the name for the new plugin repository.

2. In the newly created repository, start a new Github Codespace and generate the plugin structure.

Run the following command to create a new Nomad plugin project using cookiecutter-nomad-plugin:

```sh
cruft create https://github.com/FAIRmat-NFDI/cookiecutter-nomad-plugin
```

Cookiecutter prompts you for information regarding your plugin:

```no-highlight
full_name [John Doe]: Citizen Kane
email [john.doe@physik.hu-berlin.de]: citizen@kane.de
github_username [foo]: kane
plugin_name [foobar]: awesome
module_name [awesome]: awesome
short_description [Nomad example template]: An awesome plugin for nomad
version [0.1.0]:
Select license:
1 - MIT
2 - BSD-3
3 - GNU GPL v3.0+
Choose from 1, 2, 3 [1]: 2
include_schema [y/n] (y): y
include_normalizer [y/n] (y): n
include_parser [y/n] (y): y
include_app [y/n] (y): n

INFO:post_gen_project:Initializing python for schema - src
..
INFO:post_gen_project:Remove temporary folder: licenses
INFO:post_gen_project:Remove temporary folder: macros
INFO:post_gen_project:Remove temporary folder: py_sources
```




There you go - you just created a minimal nomad plugin:

> [!NOTE]
> In the above prompt, we pressed `y` for schema and parser, this creates a python package with two plugins one for parser and one for schema.

```no-highlight
nomad-awesome/
├── LICENSE
├── README.rst
├── pyproject.toml
├── move_template_files.sh
├── src
│   └── noamd_awesome
│       ├── __init__.py
|       ├── schema
│       |   ├── __init__.py
│       |   └── plugin.py
|       └── parser
│           ├── __init__.py
│           └── plugin.py
|
├── tests
│   ├── conftest.py
│   └── test_awesome.py
└── MANIFEST.in
```


> [!NOTE]
> The project `nomad-awesome` is created in a new directory, we have included a helper script to move all the files to the parent level of the repository.


```sh
sh CHANGE_TO_PLUGIN_NAME/move_template_files.sh
```

> [!IMPORTANT]
> The `CHANGE_TO_PLUGIN_NAME` should be substituted by the name of the plugin you've created. In the above case it'll be `sh nomad-awesome/move_template_files.sh`. 


