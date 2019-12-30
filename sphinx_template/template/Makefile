# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

BLUE=\033[0;34m
NC=\033[0m# No Color

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
	@echo "  ${BLUE}deploy${NC}      to deploy the generated documentation to the docs directory"

.PHONY: help Makefile


# Put here the path to the source folder
export PYTHONPATH=../src

deploy:
	@echo "Deploying documentation into the ${BLUE}docs${NC} folder"
	@rm -r ../docs
	@cp -a build/html/ ../docs

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	#sphinx-apidoc -o source ../src/
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

