# Buzz: Feed aggregator

Minimal version of [liferea](https://lzone.de/liferea/) feed reader in python3 and pyside library.


Main page                                                                      |  Add new subscription
:-----------------------------------------------------------------------------:|:-------------------------:
![](https://github.com/priyesh9875/buzz/blob/master/Screen/main%20screen.png)  |  ![](https://github.com/priyesh9875/buzz/blob/master/Screen/adding%20item.png)

Subscription added                                                            |  Context menu
:----------------------------------------------------------------------------:|:-------------------------:
![](https://github.com/priyesh9875/buzz/blob/master/Screen/item%20added.png)  |  ![](https://github.com/priyesh9875/buzz/blob/master/Screen/context%20menu.png)

File menu                                                                   |  Search result
:--------------------------------------------------------------------------:|:-------------------------:
![](https://github.com/priyesh9875/buzz/blob/master/Screen/file%20menu.png) | ~![](https://github.com/priyesh9875/buzz/blob/master/Screen/search%20result.png)



-----
###  Steps(for linux system, respective equivalents are applicable on other system):

#### Required libraries:

1. pip3: sudo apt install python3-pip
2. pyside: sudo apt install python3-pyside or pip3 install pyside 
3. pyside-tools: sudo apt install pyside-tools (for generating *.py files from *.ui files)
4. pyinstaller: pip3 install pyinstaller (for building standalone builds)
5. feedparser: pip3 install feedparser
6. moment: pip3 install moment


#### Steps

- Executing:
	1. cd dist && ./app
	or
	2. python3 app.py

- To change design
	1. Open *.ui files in Qt Designer
	2. pyside-uic filename.ui -o filename.pyinstaller

- Add resource files
	1. Copy res file in images directory
	2. Edit res.qrc file
	3. Compiled resource files: pyside-rcc res.qrc -o res_rc.py -py3
	   Note: 
			Output file must be res_rc.py, 
			-py3 is must for python3 interpreter


*Note: Some features may not work as they are not complete*

----
### App architecture
- Folders

    1. *build/*: Contains build files, auto generated by pyinstaller.

    2. *dist/*: Contains excutable files, generated by pyinstaller.

    3. *images/*: Contains image resources to be used in app. All image resource must be added in res.qrc filebefore using in in code.

    4. *designer/*: Contains *.ui files which are generated by QtDesigner. Not to be edited directly.

    5. *view/*: Contains view(ui) files, compiled **.ui from designer directory by pyside-uic compiler . Not to be edited directly. Modify designer file using QtDesigner and recompile *.ui file.

    6. *controller/*: Container controller and modal part of MVC architecture. It contains all controlling components of the app.

    7. *helpers/*: Contains helper function used across the app.

    8. *config/*: Currently contains only database files.


- Files

    1. *app.py*:
        - App entry point. 
	    - Initilizeses all components, connect required signals and slots.

    2. *res_rc.py*:
        - Generated by pyside-rcc. *Not to be edited*.

    3. *app.spec*:
        - Generated by pyinstaller. *Not to be edited*.
