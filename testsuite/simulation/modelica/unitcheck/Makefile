TEST = ../../../rtest -v

TESTFILES = \
UnitCheck1.mos \
UnitCheck2.mos \
UnitCheck3.mos \
UnitCheck4.mos \
UnitCheck5.mos \
UnitCheck6.mos \
UnitCheck7.mos \
UnitCheck8.mos \
UnitCheck9.mos \
UnitCheck10.mos \
UnitCheck11.mos \
UnitCheck12.mos \
UnitCheck13.mos \
UnitCheck14.mos \
UnitCheck15.mos \
UnitCheck16.mos \
UnitCheck17.mos \
UnitCheck18.mos \
UnitCheck19.mos \
UnitCheck20.mos \
UnitCheck21.mos \
UnitCheck22.mos \
ticket3631.mos \


# Tests that currently fail. Move up when fixed.
# Run make failingtest
FAILINGTESTFILES = \


# Dependency files that are not .mo .mos or Makefile
# Add them here or they will be cleaned.
DEPENDENCIES = \
*.mo \
*.mos \
Makefile \
OFunitcheck \

CLEAN = `ls | grep -w -v -f deps.tmp`

.PHONY : test clean getdeps failingtest

test:
	@echo
	@echo Running tests...
	@echo
	@echo OPENMODELICAHOME=" $(OPENMODELICAHOME) "
	@$(TEST) $(TESTFILES)

# Cleans all files that are not listed as dependencies
clean:
	@echo $(DEPENDENCIES) | sed 's/ /\\|/g' > deps.tmp
	@rm -f $(CLEAN)

# Run this if you want to list out the files (dependencies).
# do it after cleaning and updating the folder
# then you can get a list of file names (which must be dependencies
# since you got them from repository + your own new files)
# then add them to the DEPENDENCIES. You can find the
# list in deps.txt
getdeps:
	@echo $(DEPENDENCIES) | sed 's/ /\\|/g' > deps.tmp
	@echo $(CLEAN) | sed -r 's/deps.txt|deps.tmp//g' | sed 's/ / \\\n/g' > deps.txt
	@echo Dependency list saved in deps.txt.
	@echo Copy the list from deps.txt and add it to the Makefile @DEPENDENCIES

failingtest:
	@echo
	@echo Running failing tests...
	@echo
	@$(TEST) $(FAILINGTESTFILES)
