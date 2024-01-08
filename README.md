# Features of ReactJS

# JSX : 
JSX is an extension to javascript. Though it is not mandatory to use JSX in react, it is one of the good features and easy to use.

# Components: 

Components are like pure javascript functions that help make the code easy by splitting the logic into reusable independent code. We can use components as functions and components as classes. Components also have a state, props which makes life easy. Inside a class, the state of each of the props is maintained.

# Virtual DOM: 

React creates a virtual dom, i.e., in-memory data -structure cache. Only the final changes of DOM has later updated in the browsers DOM.

# Javascript Expressions: 

JS expressions can be used in the jsx files using curly brackets, for example {}.  

# File Structure: 

	reatExp/
		 src/
		    index.js
		 node_modules/
		 public/
	                index.html
		 package.json


  # Installation: 

  # Create New Project by running following commands
	  mkdir reactExp
	  cd reactExp
	  npm init -y 

  # Install React Packages 

	  npm install react --save-dev
	  npm install react-dom --save-dev
	  npm install react-scripts --save-dev

  # Create a folder src/ where all the js code will be placed 

    Create a file index.js and add import react and react-dom, as shown below. 
   # index.js

     import React from 'react';
     import ReactDOM from 'react-dom';

     ReactDOM.render(
	<h1>Hello, Happy New Year!</h1>,
		document.getElementById('root')
	);

Create a folder public/ and add index.html in that as shown below

# index.html

	<!DOCTYPE html>
	<html>
	  <head>
	    <meta charset="UTF-8" />
	    <title>React App</title> 
	  </head>
	  <body>
	    <div id = "root"></div>
	  </body>
	</html>

# Add the command in package.json that will take care of using react-scripts to compile the code and start server as shown below:

 "scripts": {
    "start": "react-scripts start" 
  }

# To start testing reactjs run the command

	npm run start

![image](https://github.com/anjaliinfo/reactExp/assets/98171488/1114c7c8-c55c-47ad-b526-856dfacae178)

It will open browser with url http://localhost:3000/ 

# Components as functions

# test.jsx

	import React from 'react';
	import ReactDOM from 'react-dom';
	function Hello() {
	    return <h1>Hello, from Anjali!</h1>;
	} 
	const Hello_comp = <Hello />;
	export default Hello_comp;

now use this component in index.js file as shown below:

# index.js

import React from 'react';
import ReactDOM from 'react-dom';
import Hello_comp from './test.jsx';

ReactDOM.render(
    Hello_comp,
    document.getElementById('root')
);

# Class as Component
# test.jsx
	import React from 'react';
	import ReactDOM from 'react-dom';
	
	class Hello extends React. Component {
	  render() {
	    return <h1>Hello, from Anjali!</h1>;
	  }
	}
	export default Hello;

We can use Hello component in index.js file as follows: 

# index.js

	import React from 'react';
	import ReactDOM from 'react-dom';
	import Hello from './test.jsx';
	
	ReactDOM.render(
	    <Hello />,
	    document.getElementById('root')
	);

# Example of states - 
# complife.jsx
	import React from 'react';
	import ReactDOM from 'react-dom';
	class COMP_LIFE extends React.Component {
	  constructor(props) {
	    super(props);
	    this.state = {name: ''};
	
	    this.UpdateName = this.UpdateName.bind(this);
	    this.testclick = this.testclick.bind(this);
	  }
	
	  UpdateName(event) {
	    this.setState({name: event.target.value});
	  }
  
	  testclick(event) {
	    alert("The name entered is: "+ this.state.name);
	  }
  
	  componentDidMount() {  
	    console.log('Mounting State : calling method componentDidMount');
	  }   
 
	  shouldComponentUpdate() {  
	    console.log('Update  State : calling method shouldComponentUpdate');
	    return true;
	  }  

	  componentDidUpdate() {  
	    console.log('Update  State : calling method componentDidUpdate')  
	  }  
	  componentWillUnmount() {  
	    console.log('UnMounting State : calling method componentWillUnmount');
	  }  

	  render() {
	    return (
	      <div>        
	         Enter Your Name:<input type="text" value={this.state.name} onChange={this.UpdateName} /><br/>        
	        <h2>{this.state.name}</h2>
	        <input type="button" value="Click Here" onClick={this.testclick} />
	      </div>
	    );
	  }
	}

       export default COMP_LIFE; 

# index.js

	import React from 'react';
	import ReactDOM from 'react-dom';
	import COMP_LIFE from './complife.jsx';
	
	ReactDOM.render(
	    <COMP_LIFE />,
	    document.getElementById('root')
	); 

	![image](https://github.com/anjaliinfo/reactExp/assets/98171488/932b5faf-9d40-4d26-bced-7f70775581e1)  

# Forms Example  

form.jsx
	
	import React from 'react';
	import ReactDOM from 'react-dom';
	class Form extends React.Component {
	  constructor(props) {
	    super(props);
	    this.state = {name: ''};
	
	    this.UpdateName = this.UpdateName.bind(this);
	    this.formSubmit = this.formSubmit.bind(this);
	  }
	
	  UpdateName(event) {
	    this.setState({name: event.target.value});
	  }
	  
	  formSubmit(event) {
	    alert("The name entered is: "+ this.state.name);
	  }
	
	  render() {
	    return (
	      <form>        
	         Enter Your Name:<input type="text" value={this.state.name} onChange={this.UpdateName} /><br/>        
	        <h2>{this.state.name}</h2>
	        <input type="submit" value="Submit" onClick={this.formSubmit} />
	      </form>
	    );
	  }
	}

	export default Form;

	index.js
	
	import React from 'react';
	import ReactDOM from 'react-dom';
	import Form from './form.jsx';
	
	ReactDOM.render(
	    <Form />,
	    document.getElementById('root')
	); 

	![image](https://github.com/anjaliinfo/reactExp/assets/98171488/1d72ad49-7894-4a74-921e-f2c5e919f318) 

# Events in ReactJS 

	import React from 'react';
	import ReactDOM from 'react-dom';
	class EventExp extends React.Component {
	  constructor(props) {
	    super(props);
	    this.state = {name: ''};
	
	    this.UpdateName = this.UpdateName.bind(this);
	    this.testclick = this.testclick.bind(this);
	  }
	
	  UpdateName(event) {
	    this.setState({name: event.target.value});
	  }
	  
	  testclick(event) {
	    alert("The name entered is: "+ this.state.name);
	  }

	  render() {
	    return (
	      <div>        
	         Enter Your Name:<input type="text" value={this.state.name} onChange={this.UpdateName} /><br/>        
	        <h2>{this.state.name}</h2>
	        <input type="button" value="Click Here" onClick={this.testclick} />
	      </div>
	    );
	  }
	}

	export default EventExp;


   Index.js

	import React from 'react';
	import ReactDOM from 'react-dom';
	import EventExp from './events.jsx';
	
	ReactDOM.render(
	    <EventExp />,
	    document.getElementById('root')
	); 
	

