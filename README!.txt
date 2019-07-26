Documentation Author: Niko Procopi 2019

This tutorial was designed for Visual Studio 2017 / 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

Welcome to the Window Creation Tutorial!
Prerequesites: Core C++

The first thing we need to do before rendering 3D graphics is 
to create the window. We will be using GLFW and GLEW for this

glfwWindowHint will set parameters for what our window will
do, prior to creation of the window.

We want to let GLFW know that we will be using OpenGL 3.3
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
	
We do not want the window to be resizable, because that can
cause problems later on
	glfwWindowHint(GLFW_RESIZABLE, GL_FALSE);
	
After our parameters are set, we can finally make the window
	GLFWwindow* window = glfwCreateWindow(WIDTH, HEIGHT, 
						"Opening a window", nullptr, nullptr);
						
WIDTH and HEIGHT are set near the top of the screen as 800 and 600,
"Opening a window" will be displayed in the window's title bar, feel
free to change these to whatever you want.

Further down the screen we set our Viewport. Viewport is the region of the
screen that we want to draw to, which is all of it
	glViewport(0, 0, screenWidth, screenHeight);
	
GLFW gives us a boolean to determine if the window should be closing:
	glfwWindowShouldClose(window)
	
This boolean becomes true when the window is closed. Notepad, Firefox,
Google Chrome, and all other programs have minimize buttons and close 
buttons. If we dont tell the window to close when the close button is pressed,
nothing will happen.

GLFW already detects when the button is hit, and it sets
	glfwWindowShouldClose(window)
	to be true, and then we close.
	
We have a loop to continuously draw to the screen:
	while (!glfwWindowShouldClose(window))
	
Then the program ends after that loop, and the window is 
closed by glfwTerminate();

Inside the loop, we check for keyboard input
or the close button on the window being hit,
	glfwPollEvents();
	
We set the color that we want the screen to clear to
	glClearColor(0.2f, 0.3f, 0.3f, 1.0f);
	
We actually do the clearing of the screen:
	glClear(GL_COLOR_BUFFER_BIT);
	
And we pass the image we just made (cleared image) to the screen:
	glfwSwapBuffers(window);
	
Congratulations, you're done, you have a window
	

