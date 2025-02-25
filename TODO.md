ani-cli-batch is a mess. I'm planning on refactoring the code so others can actually work on it and contribute too. 
This document will keep track of the project and provide relevant documentation.

## To Do
### Refactoring
- [ ] Use a proper queue management system instead of storing the entire queue in a variable
- [ ] Change the updater to an installer
	- [x] Have the installer make a config directory
	- [x] Have the installer populate the config directory properly
	- [x] Add Android support
	- [ ] Rename ani-cli-batch-update ?
### Add new features
- [ ] Support to pass arguments to ani-cli
- [ ] Support running with the python version of ani-cli
- [ ] Add support for a download destination argument
- [x] Add a check for updates option in the menu
