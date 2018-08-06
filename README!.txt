Setting up GLFW and GLEW

Download the pre complied binaries for GLFW and GLEW from the given webpages.
NOTE: Download the 32 bit binaries
GLFW: http://www.glfw.org/download.html
GLEW: http://glew.sourceforge.net/

Extract the binaries put it in a place you'll remember

Create an empty Visual Studio project.

Go to the project properties:

1)	Go to C/C++ -> General
	Go to "Additional Include Directories"
	Locate and add the paths to the include folders of GLFW and GLEW here
	
	The paths should look something like GLFW/include and GLEW/include

2)	Go to Linker -> General
	Go to "Additional Library Directories"
	Locate and add the paths to the libraries of GLFW and GLEW
	
	The paths should look something like GLFW/lib-vc2015 and GLEW/lib/Release/Win32
	
3)	Go to Linker -> Input
	Go to "Additional Dependencies"
	Add the following .lib in here:
		opengl32.lib
		glew32s.lib (OR glew32.lib if you don't want static lib)
		glfw3.lib
		
4)	Apply the changes and you are all set


NOTE: The libraries and directories for the project have already been included in this project,
	  if you encounter any linking errors, please make sure all the libraries and directories
	  are properly attached