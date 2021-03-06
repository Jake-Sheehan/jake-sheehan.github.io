# Introduction

  Hello, my name is Jake Sheehan and I am a recent graduate of the Computer Science program at Southern New Hampshire University. I have a passion for FinTech, especially emerging blockchain solutions. FinTech and blockchain technologies have the potential to change the change the world by bringing financial services to the 1.7 billion unbanked adults around the world, spurring economic development and helping to alleviate poverty in traditionally hard-to-reach parts of the globe. My hope is that by contributing to this technology as a developer, I can help to advance these goals by developing new, innovative technologies that bring economic freedom to everyone.

  This ePortfolio is intended to showcase my skills related to my career goals. To do so, I have selected three projects that I worked on throughout my time at Southern New Hampshire University. I conducted a code review of the assignments to detail some of the strengths and weaknesses in the code base. Then, I designed enhancements to these projects that will improve on the weaknesses, and tailor the project toward my career goals.

  The three projects are aligned with three topics: software engineering and design, data structures and algorithms, and databases. In the category of software engineering and design, I chose to further develop an OpenGL-based graphics rendering engine. This was one of the larger, more complex projects I worked on as a student, and it required careful architecture design. To showcase my skills in data structures and algorithms design, I chose to convert a binary tree I wrote for one of my classes into a Merkle tree. Merkle trees are commonly used in blockchain software, with the root hash of the tree representing a “block” on the blockchain. Finally, to demonstrate my ability to work with databases, I converted a small SQL-based contact storage application into a full graphical application with a cloud-hosted non-relational database.

  These projects cover a wide array of topics and represent a culmination of the education I received at Sothern New Hampshire University. This long journey would not have been possible without collaborating with fellow students and my professors to produce the best possible Computer Science artifacts. I would like to thank everyone that helped me along the way and acknowledge the teamwork that produced these results.


# Project One: OpenGL Graphics Rendering Engine 
### [VIEW CODE REVIEW ON YOUTUBE](https://www.youtube.com/watch?v=MwRLEhmv-zg)
### [VIEW ORIGINAL ON GITHUB](https://github.com/Jake-Sheehan/rendering_engine_original)
### [VIEW ENHANCEMENT ON GITHUB](https://github.com/Jake-Sheehan/rendering_engine)
  
### What is it?

  The first artifact in my ePortfolio demonstrates my skills in software design and engineering. For this project, I chose to enhance a graphics rendering engine that I began developing in a computer graphics and visualization class earlier this year. The project uses OpenGL to render graphics using the graphics card directly, and the GLFW library to handle operating system calls for window creation and user input. Models are created in third-party software, like Blender, and then exported to a wavefront object. My rendering engine can import wavefront objects, position them in the scene, and then render the scene in a window. The keyboard can be used to move the camera around the scene, and the mouse can be used to look at objects.

### Why was it selected?

  I selected this project for my artifact to demonstrate my ability to create computer graphics by programming directly on the graphics card. In the future, I hope to work in the financial technology industry, and data visualization is vital to this industry. While many third-party libraries currently exist to visualize data, having the ability to program graphics directly on the graphics card allows for complete customization and control of system resources. In the financial industry, it is often necessary to have the most up-to-date information possible. Running C/C++ code directly on a graphics card will provide far greater performance than a third-party GUI library can.

### Reflection on the process

  Coming into this Capstone class, my graphics rendering engine was not fully complete. The code compiled, but it was disorganized and not very readable. This was especially true of my lighting model. My software uses the Phong lighting model, which uses ambient, diffuse, and specular lighting to create realistic lighting graphics. In my code, the model was implemented in the main function and used hardcoded numbers to instantiate a light source. While this strategy worked, it did not demonstrate careful software design practices. To enhance the code, I encapsulated the code in a new light source class. This was a sub class of the more general model class but added features specific to the lighting model. Now, you can instantiate a light source object by detailing the relative path to the wavefront object, ambient light color, diffuse light color, specular light color, and the ambient strength. This improvement makes the code more readable and reusable.
  
  During the process of enhancing my artifact, I did encounter some challenges. By encapsulating the lighting model in its own class, I moved the code away from the main function. This meant that the code no longer had direct access to the shader programs. To solve this problem, I had to pass both shader programs as parameters. Another problem I had involved sharing the project using GitHub. The program imports wavefront objects from third-party software like Blender. These wavefront objects have a .obj file extension. The problem is that Visual Studio produces its own files, not related to graphics, that use the same extension. By default, Git ignores any files with that extension. I needed Git to include my wavefront .obj files but exclude the built-in Visual Studio .obj files. To solve this problem, I changed the wavefront files extension to a .object extension. This allowed Git to ignore the Visual Studio files but include my wavefront files to share with others.

# Project Two: Merkle Tree Implementation in C++

### [VIEW CODE REVIEW ON YOUTUBE](https://www.youtube.com/watch?v=ZfkT7gE-Fx0)
### [VIEW ORIGINAL ON GITHUB](https://github.com/Jake-Sheehan/BinaryTree)
### [VIEW ENHANCEMENT ON GITHUB](https://github.com/Jake-Sheehan/MerkleTree)

### What is it?

  The second artifact in my ePortfolio demonstrates my ability to work with algorithms and data structures. For this project, I chose to convert my binary tree into a Merkle tree. I developed the binary tree code when I took a data structures and algorithms course. The binary tree sorts data as it is taken as input into the tree making it much easier to retrieve the data later. A Merkle tree is a type of binary tree that can be used to verify that blocks of data have not been altered. This is useful in peer-to-peer networks to guarantee the integrity of data transmitted over the network. To do this, the blocks of data make up the bottom level of the tree. The data blocks are hashed using any hashing algorithm that outputs a fixed length digest. In this case, I used the industry standard SHA256 hashing algorithm. Pairs of block hashes are concatenated and hashed together, to form a parent hash. If the number of blocks is odd, the last hash will be concatenated with itself and hashed. This process continues level after level until a root hash is generated. The root hash will always be the same if the same blocks are fed into the Merkle tree in the same order, but if any block has been altered, the root hash will be different. Furthermore, to verify any one block, you only need one block per level of the tree. When used with large amounts of data, a Merkle tree can greatly reduce the time needed to verify a single block.
  
### Why was it selected?
  
  I chose to include a Merkle tree in my ePortfolio because they are often used to verify financial transactions, especially in blockchain solutions. Implementing a Merkle tree not only shows skill in programming, but it shows that I can implement algorithms that are heavily used in the industry today. This project also required working with modern C++ encryption libraries. Since even the smallest security flaw in the implementation could be fatal to encryption procedures, most professional developers prefer to work with well-known open-source libraries as opposed to implementing their own. For this project, I chose to work with CryptoPP, a standard library used in modern software projects, to demonstrate my ability to work with such libraries.

### Reflection on the process

  Overall, I met my objectives with this enhancement. My Merkle tree implementation functions well and follows best practice standards. I included some test code that manually calculates a root hash, and then compares the hash to one generated by my Merkle tree. When the code is run, you can see that both hashes are identical, and the CryptoPP library is used to verify them as well. One of the challenges I faced was that the algorithm to generate the root hash must be recursive because we do not know ahead of time how many blocks will be in the set, therefore we do not know how many levels the tree will have. Recursive algorithms can be difficult to implement, and it took a bit of trial and error until I got it right.

# Project Three: Cloud-Based Contacts App

### [VIEW CODE REVIEW ON YOUTUBE](https://www.youtube.com/watch?v=f6DU-FTMvh4)
### [VIEW ORIGINAL ON GITHUB](https://github.com/Jake-Sheehan/Contacts_original)
### [VIEW ENHANCEMENT ON GITHUB](https://github.com/Jake-Sheehan/Contacts)

### What is it?

  The third artifact in my ePortfolio demonstrates my ability to work with databases. For this artifact, I chose to enhance an application that stored contact information including name, phone number, and email in a database. This application was originally developed in a database class I took earlier in 2021, and it used command line operations to store data locally. To improve the application, I added a graphic user interface using the Tkinter library and hosted the database in the cloud using an mLab MongoDB database-as-a-service solution. Now, you can run the application with a GUI and access your contacts from anywhere.

### Why was it selected?

  I selected this item to include in my ePortfolio because it illustrates my ability to work with modern database solutions. Today, it is rare to find applications that operate completely on a local machine. Since most users these days have multiple devices, it is more common that applications save data to cloud-based databases so that users can retain their data and application state between those different devices. While this project is simple, using only one database and three data fields, it would not be difficult to expand it to include multiple databases, collections, and data fields. I could simply use the API in this program to add or remove any database objects that I need to.

### Reflection on the process

  My goal for the enhancement process was to improve the original application to make it easier for the user to navigate. My enhancements to the graphic user interface improve the application by adding text entry boxes to enter new contact information, an “add” button to add the new information to the application and the database, and a “delete” button that will remove the selected item from the application and the database. The interface is clean and organized, and the text entry boxes contain placeholder values that show which data field the box represents. The placeholders disappear when the box is clicked and reappear after an empty box loses focus or the add button is clicked. Any entry in the contacts list can be removed, no matter the location in the list, and the list will properly re-adjust to correctly display the remining items. Overall, the goals for this enhancement were met.

  During the development of this application, I faced some challenges and learned some important lessons. When approaching GUI development, I did not examine the library close enough. I started creating my own list-type structure using Label elements from Tkinter before realizing that Tkinter already had a built-in Treeview structure that displayed lists. I didn’t realize this until I tried to implement a scrollbar toward the end of the development process and realized that it would not be feasible. I ended up re-designing the contacts list to use a Treeview element that had built-in scrollbar functionality. I learned that it is important to read the documentation thoroughly before starting the design process. Also, I had some challenges getting the cloud-based database to function. There was a problem with SSL certificates that I had to work through. I learned how to troubleshoot these types of issues using documentation and forums. In the end, I figure out that I needed to download the latest certificates from Let’s Encrypt, and I needed to notify my users that they would need to do the same if they had not done so yet.
