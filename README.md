### EXPLANATION

- Normal coding generates spaghetti code i.e the code is shattered all over the application.

- In such a condition, reading the source code, making changes or adding additional functionality on top of the original code becomes way too difficult, be it a different developer or the same developer.

- For bigger applications, the problem becomes even more persistent. Therefore, to avoid this, the best choice developers could make is to create separations in their code. This means the same as it sounds - dividing the code according to its functionality. The whole idea is to separate out the logical part of our code(states) from other parts such as the UI elements.

- By separating the logical part, we can control the inputs and outputs for the logical components, which in turn will reduce the number of errors that we’ll face. Apart from that, while working with bigger codebases, having different components at different locations helps the developers divide the work efficiently, eg : one team could work on the UI elements while the other could work on the logical components. Having all the components together would have messed everything up.

- To achieve this, there are various frameworks, applications and libraries. One such method is known as BLoC or Business Logic Components.

- In BLoC pattern, there are three major terminologies involved : 

         - Sink(inputs)

         - Stream(outputs)

         - Stream Controller(process)

- Let’s consider a simple scenario : We have our logical component which handles all the computations and calculations. We have two UI elements(widgets), one for taking input(like a button) and one for displaying the output(like a text viewer widget). Now, if the user clicks the button, certain computations must be done and a text should be displayed on the screen. The developers need not know the computational part, they just need to look at the UI components. Therefore, we can separate the logical components from the UI elements in such a way that they are connected, but not visible in that portion.

- The inputs can be referred to as the sink, the outputs as the stream and the logical component as the stream controller.

- The sink listens to the stream controller via a listener component and the stream flushes out the output generated. The stream must always be closed to avoid data leakage.

- There are two kinds of BLoC systems :

        - Single User Subscription : When only one user/sink can listen to the stream controller at a time.

        - Broadcasting : When multiple users/sinks can listen to the stream controller simultaneously. 





### CODING

- There are two kinds of widgets - Stateless widgets and Stateful widgets. The former is used when the widget doesn’t change or the user cannot interact with the widget(like icons, buttons etc) and the latter is used when the user can change/interact with the widget(like a list viewer widget).

- The entire code would be divided into multiple files. It’s up to the developer, what files they want to create and how many separations they want. For basics, one can start by creating these files :

        - main.dart : For starting the app.

        - homepage.dart : For UI components(inputs and outputs).

        - components.dart : For defining classes and variables related to different components involved in the app. Also for declaring the setters and getters                                 required.

        - componentBloc.dart : For implementing the BLoC functionality in the app i.e. connecting all the above files efficiently and neatly.

- Once everything is set-up, the BLoC pattern can be implemented in the dedicated files.

- To implement the BLoC pattern, there are certain things which we need. These are :

        - Some imports

        - List of components involved

        - Stream controllers

        - Stream/Sink getters

        - Constructors

        - Core functions

        - Disposal method(s)
