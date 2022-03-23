# What are VS Code and PyCharm?

[VS Code](https://code.visualstudio.com) and [Pycharm](https://www.jetbrains.com/pycharm/) are both Integrated Developement Environments, or IDEs. You've probably worked with an IDE, RStudio is an IDE. Ultimately the purpose of an IDE is to make coding easier. Some of the most basic features of IDEs are syntax highlighting and autocompletion capabilities, but they can also do a lot more than that - like displaying hover-over metadata (eg displaying a function's documentation when hovering over code), jumping to the part of the file where a function is defined/used, showing where an error will occur, among others. While PyCharm is specifically built for python (but see other IDEs from [jet brains](https://www.jetbrains.com)), VS Code supports hundreds of coding languages.

Both PyCharm and VS Code have free professional versions for students and academics - see eg here for [PyCharm](https://www.jetbrains.com/community/education/#students). I won't say much more about the purposes and cool features of these IDEs, for that it would be good to google, use the intro/how-to resources from each program's page, or better yet open one up and explore.

The purpose of this post is to show how to set up VS Code and PyCharm to connect to NEU's Discovery cluster. 

- [ ] First download and install the program by visiting the landing pages linked above.
- [ ] Make sure you can ssh to discovery - in terminal `ssh user@discovery.neu.edu`
  - TODO - link to example of ssh config
  - to set up passwordless ssh so you don't have to enter a password each time, see [this link](http://www.linuxproblem.org/art_9.html)

---

## VS Code
- Install the [Remote Development Extensionpack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
<img src="https://user-images.githubusercontent.com/8821725/159176412-c43f26ad-855a-46d8-918a-31bf41156bea.png" width="600" height="400">

- Once the Remote Development Extension is installed, open the Command Palette (⇧⌘P) and type "<b>Remote-SSH: Connect to Host...</b>" and you should see something like this ![Screen Shot 2022-03-23 at 9 39 21 AM](https://user-images.githubusercontent.com/8821725/159713469-dcb1aebc-915e-495f-89b1-d3ca29ff7fd0.png)
- After a moment, VS Code will connect to the SSH server and set itself up. VS Code will keep you up-to-date using a progress notification. After you are connected, you'll be in an empty window. You can always refer to the Status bar to see which host you are connected to. <br>![Screen Shot 2022-03-23 at 9 45 28 AM](https://user-images.githubusercontent.com/8821725/159713970-a6471acf-e7db-4b43-a87f-316ee8feb9a5.png)</br>
- You should now be able to choose the folder you wish to open <br> ![Screen Shot 2022-03-23 at 9 48 16 AM](https://user-images.githubusercontent.com/8821725/159714594-fa30ac5e-3666-492a-abb9-52de33fa2879.png)</br>
- After opening the folder destination you can begin to create new files or open that already exist ![Screen Shot 2022-03-23 at 9 50 56 AM](https://user-images.githubusercontent.com/8821725/159715126-e0cc754b-ddb3-43ea-98a1-a1fa6a665f16.png)

---

## PyCharm

- After setting up a project first add the Remote Host tool window to the sidebar![Screen Shot 2022-03-23 at 10 07 10 AM](https://user-images.githubusercontent.com/8821725/159718453-3750eb37-6127-4c53-9e00-ffec62ba4a22.png)
- If PyCharm opens the Remote Host tool window like a browser tab, you can drag it to the sidebar. Afterwards, click on it. Then click on the `...` next to the drop down menu. In the Deployment window, click the `+` button to add a new SFTP connection. This will then prompt you to give a server name, let's use "discovery".<br>
![Screen Shot 2022-03-23 at 10 11 28 AM](https://user-images.githubusercontent.com/8821725/159719312-ca86411a-1d7d-4131-95a3-fa894d6eee94.png)</br>
- Next we need to set up the SSH Configuration - click the `...` next to the SSH Configuration drop-down menu. Fill in your credentials. I have passwordless ssh already configured (how-to link above) so I have selected to authenticate using my RSA key. Make sure to test the connection. <br>![Screen Shot 2022-03-23 at 10 19 02 AM](https://user-images.githubusercontent.com/8821725/159720760-74429eab-6aa7-4a5e-bbb9-eb3672879f72.png)</br>
- Close the SSH Configuration window to return to the Deployment window. Test the connection in the Deployment window. After a successful connection, close the Deployment window and select 'discovery' from the Remote Host drop-down menu. You should now be able to browse files on the remote server.![Screen Shot 2022-03-23 at 10 22 20 AM](https://user-images.githubusercontent.com/8821725/159721461-d1106690-d6f9-452d-983e-02913f4b625c.png)



