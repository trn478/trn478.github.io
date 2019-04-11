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

You have to make sure to go to **Firebase.js** and plug in your 
configurations that is specified in **Project Overview** in Firebase Console.

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


**Creating Form & Input**
----

Firstly, let's create a form where users can type in their messages

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ javascript
# App.js
render() {
    return (
      <form onSubmit={this.onAddMessage}>
        <input type="text" ref={node => this.input = node}/>
        <input type="submit"/>
        <ul>
          {this.state.messages.map(message =>
            <li key={message.id}>{message.text}</li>
          )}
        </ul>
      </form>
    );
 }
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

I have built the form in App.js for simplicity but you should create a 
separate component, like Form.js for forms to enhance its features.


**Creating a Message**
----

Our message will only contain one property, the s.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ javascript
  constructor() {
      super();
      this.state = {
        messages: [],
      };
    }
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


**Handling Events**
----

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ javascript
  componentWillMount() {
    const messagesRef = database.ref('messages')
      .orderByKey()
      .limitToLast(300);
    # Snapshot message and store it
    messagesRef.on('child_added', snapshot => {
      const message = { text: snapshot.val(), id: snapshot.key };

      this.setState(prevState => ({
        messages: [ message, ...prevState.messages ],
      }));
    });
  }
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When user inputs a message.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ javascript
  onAddMessage(event) {
    event.preventDefault();
    # Push input to messages
    database.ref('messages').push(this.input.value);
    # Set input back to empty string
    this.input.value = '';
  }
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


**Running the App**
----
If you made it this point, you have a simple messaging web app. Let's run it.

    npm start
    
This is a simple use of **React + Firebase**. Feel free to modify the code for your own use!

Cheers! 
