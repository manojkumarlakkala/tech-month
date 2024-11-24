
Things you'll learn:
- Building a counter
- Dark theme to Light theme
- Simple Text input
- Scroll view 

## Building a  Counter

```jsx
import React,{useState} from 'react';
import {View,Button} from 'react-native';

export default app(){
	const [count,setCount] = useState(0); //initializing the count state with 0
	function handleClick(){
		setCount(count+1);
	}
	function reset(){
		setCount(0);
	}
	return(
		<View>
			<Button onPress={handleClick} title={count}/>{//assigning handleClick function to button to increase the count upon clicking.
			}
			<Button onPress={reset} title='Reset'/>{//setting the count to 0
			}
		</View>
	);
}
```
![[Pasted image 20241124181726.png]]

## Dark Theme to Light Theme
```jsx
import React,{useState} from 'react';
import {View,Button} from 'react-native';

export default app(){
	const [state,setState] = useState(false);//initializing useState with false.
	function handleclick(){
		setState(!state);
	}
	return(
		<View>
			{state?<Button onPress={handleclick} title='Set Light Theme'/>:<Button onPress={handleclick}title='Set Dark Theme'/>//ternary if else statement checking if the state is true, i.e dark theme else false i.e light theme
			}
			{state?<View style={{backgroundColor: 'black', color:'white'}}><Text>Hi</Text></View>:<View style={{backgroundColor:'white',color:'black'}}><Text>Hi</Text></View>}//setting the theme according to state.
		</View>
	);
}
```
This is to get a very basic idea about light to dark theme.

## Simple Text Input
```jsx
import React,{useState} from 'react';
import {View,Text,TextInput,Button} from 'react-native';

export default function app(){
	const [text,setText]=useState('');
	return(
		<View>
			<TextInput 
				onChangeText={setText}//sets the text state to the changed value in the input
				placeholder="Enter to show in input box"//shows up in the input box before entering anything
				value={text}//the value entered in the input
			/>
			<Text>{text}</Text>
		</View>
	);
}
```
![[Pasted image 20241124180406.png]]
![[Pasted image 20241124180441.png]]
## ScrollView
```jsx
import React from 'react';
import {useState,View,Text,ScrollView} from 'react-native';

export default function app(){
	return(
		<ScrollView>
			{
				//enter your items here
			}
		</ScrollView>
	);
}
```
![image](https://miro.medium.com/v2/resize:fit:700/1*PyHpvhb9EPWGcSVLp1VzRQ.gif)
