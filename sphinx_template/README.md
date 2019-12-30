Installation
------------

1. Install Sphinx and some of its extensions, located at `requirements.txt`

2. Copy the the folders `docs` and `docsrc` to the root directory of your project.

- The `docs` folder is empty and it will contain the generated and deployed documentation generated with Sphinx.

- The `docsrc` has the following contents:

  - `Makefile`: this is the make file to be used to generate the documentation.
  - `source` folder: put your documents here. It contains 4 files:
    - `conf.py` this is the configuration file for document generation.
    - `genindex.rst`: do not modify this file. Just keep it as it is.
    - `index.rst`: this file defines the whole structure of the documentation. Include here all those documents you
      want to add.
    - `module_index.rst`: this file specifies


Configuration
-------------

- Modify the `conf.py` file

  - To set the location of the code sources folder/s:

    `sys.path.insert(0, os.path.abspath('../src')`

  - To add information about the project:

    - project name
    - version
    - release
    - description
    - etc.

- Optionally if the location of the source folders is not set in `conf.py` it is possible to be set using the PYTHONPATH environment variable.
  `export PYTOHPATH=../src`


Writing the documentation
-------------------------

While markdown (MD) format is supported it is recommended to write documents in RST format since there exist some bugs in the processing
of MD files.

Include all your documents into the `docsrc/source` folder. You may organize your docs within subfolders here as you need.

- Modify the `index.rst` file: this document defines the overall structure of the documentation. You can add here any section that is needed.
  Follow the hints contained in `index.rst`.

  The last `toctree` directive adds a section with automatically generated documentation from code docstrings. Do not remove it unless you really
  need to do it.

- Modify the `module_index.rst` file: this document defines which Python modules to document int the `Reference` section of `index.rst`.
  Simply select which modules to include and add them following the examples contained in `modules_indes.rst`.


Generating the documentation
----------------------------

To generate documentation execute in the `docsrc` folder:

	make clean
	make html

The resulting documentation is generated in the folder `docsrc/build/html`.

To deploy the generated documentation to the `docs` folder:

	make deploy


Execute `make help` for more options.

	make help
