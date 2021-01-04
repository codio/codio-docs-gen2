Customizable run menu
=====================
A handy feature is the ability to add commonly used commands to the Codio IDE, akin to using the `alias` command from the command line.

When the menu item is selected, a new terminal window will open to run the command in. You can also force the command to run in an existing terminal window as we illustrate below.

.codio file
-----------
The configuration for the **Run** (and **Preview**) button can be set by editing the `.codio` file in the root of your project.

The following code below shows the `.codio` file configured to give this Run menu

.. image:: /img/run-menu.png
   :alt: Run Menu



which is driven by the following `.codio` file

.. code:: json

    {
      // Configure your Run and Preview buttons here.

      // Run button configuration
      "commands": {
        "Install Learnyounode" : "npm install -g learnyounode",
        "Run Lesson" : "./ns-executes.sh run {{filename_no_ext}} {{path}}",
        "Verify Lesson" : "./ns-executes.sh verify {{filename_no_ext}} {{path}}",
        "Completed Lessons" : "learnyounode",
        "Run with Node" : "node {{filepath}} 3 4 5"
      }
    }


When you select a **Run** command, it will open a new console window where you will see the output. Pressing the **Run** button will execute the last selected command.

Using the same terminal window
------------------------------
If you want to avoid new terminal windows appearing when you run the command, you can use an id field.

.. code:: json

    {
      "commands": {
            "Node version": {
                "id": "terminal_1",
                "cmd": "node --version"
            },
            "ls": {
                "id": "terminal_1",
                "cmd": "ls"
            }
      },

    // Preview button configuration
      "preview": {
            "Project Index (static)": "http://{{domain}}/{{index}}",
            "Current File (static)": "http://{{domain}}/{{filepath}}",
            "Box URL": "http://{{domain3000}}/"
      }
    }


- Commands with the same "id" will share the same terminal window.
- The terminal id should be "backend-guide" to execute a command in the terminal window opened by guides.



.codio Tokens
-------------
You can see from the above `.codio` sample that it is possible to insert tokens into the shell commands. The following tokens are currently available and operate in the main on the currently selected file tab in the IDE

- `{{filepath}}` inserts the path and full file name `/path/to/file.ext`
- `{{path}}` inserts only the path to the selected file `/path/to/`
- `{{filename}}` inserts the filename with its extension `file.ext`
- `{{filename_no_ext}}` inserts the filename without the extension `file`
- `{{domain3000}}` inserts the public url to your box; `word1-word2-3000.codio.io` to access over port 80, which is useful if your corporate firewall blocks ports other than 80 and 443
- `{{domain}}` inserts the alternate public url to your box; `word1-word2.codio.io`, be aware that you will usually need to specify a port to reach a service running on your Box. e.g. `word1-word2-<port>.codio.io`

