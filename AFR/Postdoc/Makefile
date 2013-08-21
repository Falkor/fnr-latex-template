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

SRC_DIR       = src
PROJECT_DESC  = $(SRC_DIR)/project_description
LETTER_INTENT = $(SRC_DIR)/personal_statement


MAIN_TEX     = $(shell grep -l "[\]begin{document}" $(SRC_DIR)/*.tex | xargs echo)
PDF          = $(MAIN_TEX:%.tex=%.pdf)

all:
	@echo "=> compiling project description in '$(PROJECT_DESC)"
	$(MAKE) -C $(PROJECT_DESC)
	@echo "=> compiling letter of intent in '$(LETTER_INTENT)"
	$(MAKE) -C $(LETTER_INTENT)
	@echo "=> generating full proposal"
	$(MAKE) -C $(SRC_DIR)
	@echo
	@echo "***** FULL PROPOSAL : $(PDF) ******"
	@echo 

%:
	$(MAKE) -C $(PROJECT_DESC)  $@
	$(MAKE) -C $(LETTER_INTENT) $@
	$(MAKE) -C $(SRC_DIR)       $@
