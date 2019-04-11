---
title: Build a Real Time chatting room using React + Firebase!
---

**Getting Started**
------

![](<../images/firebase-react.png>)

Source: [bitsrc.io](https://blog.bitsrc.io/building-a-todo-app-in-react-with-firebase-and-redux-ba3ab53a671b)

**Benefits of React + Firebase**
------

| **Stacks** | **MEAN** | **MERN** | **React + Firebase** |
|--------------|-----------------------|-------------------|--------------------|
| Server | ✓                     | ✓                 |                   |
| Database    | ✓                     | ✓                 |                   |
| Front-end       | ✓                     | ✓                 | ✓                  |
| Back-end       | ✓                     | ✓                 |                   |

By using [**Firebase**](https://firebase.google.com/) we now can develop in a **server-less** environment. 
Firebase is a *BaaS*(Backend as a Service).

**React.js** is widely used due to its reactive nature. 
It creates a virtual DOM that gets updated whenever any state changes.
Thus, performance is optimal since it re-renders only the element that has changed.

**Prerequisites**
----

First, you need [Node.js](https://nodejs.org) downloaded.

Then you would use **npm** command to install other dependencies.


**Create Firebase Project**
----
You can create a new Firebase project [here](https://console.firebase.google.com/u/0/)

Go to Firebase [**Console**](https://console.firebase.google.com/),
then go to Authentication tab and enable Anonymous.

Later on you can add other authentications, but for now let's keep it simple.

**Create React Application**
----

Now it's time to create a React App

![](<../images/react.gif>)

Install React using React CLI

    npm install -g create-react-app

Initialize your React Project and move the the directory

    create-react-app real-time-chat
    cd real-time-chat 
    
Then we have to install **Firebase** module,

    npm install --save firebase
    
Now you can run your app! Run by:

    npm start

This is what you should see 

![](<../images/react.png>)




