####################################################################################
# Makefile (configuration file for GNU make - see http://www.gnu.org/software/make/)
#
# --------------------------------------------------------------------------------
# This is a generic makefile in the sense that it doesn't require to be 
# modified when adding/removing new source files.
# --------------------------------------------------------------------------------
#
# Author: Sebastien Varrette <Sebastien.Varrette@uni.lu>
#          Web page : http://varrette.gforge.uni.lu
#

SRC_DIR      = src
PROJECT_DESC = $(SRC_DIR)/_7_1_project_description
MAIN_TEX     = $(shell grep -l "[\]begin{document}" $(SRC_DIR)/*.tex | xargs echo)
PDF          = $(MAIN_TEX:%.tex=%.pdf)

all:
	@echo "=> compiling project description in '$(PROJECT_DESC)"
	$(MAKE) -C $(PROJECT_DESC)
	@echo "=> generating full proposal"
	$(MAKE) -C $(SRC_DIR)
	@echo
	@echo "***** FULL PROPOSAL : $(PDF) ******"
	@echo 

%:
	$(MAKE) -C $(PROJECT_DESC) $@
	$(MAKE) -C $(SRC_DIR)      $@
