
Make me a webapp SPA called "Grapher". The purpose of this app is to help understand code better by being able to draw flowcharts of what function calls what function.

In the app i can select a C# folder that is a code repository. Then the webapp scans and reads all files and presents a directory view in a sidebar on the left- this has all the cs classes in a folder view where i can expand folders to view the cs files inside. If there are two classes inside a file, you have to present them as though they are different files. This is a class view, organized by folder. In the directory view you can also expand each class to see all the methods inside it. This information (for a repo) should be stored in a json (that the user can update with a button press).

The second half of the app is that the user can drag any of these methods (e.g. method A) from the sidebar directory view onto the main page, drag and drop, as a box. you can draw arrows between two boxes.