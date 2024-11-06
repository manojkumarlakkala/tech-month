# Creating the Hello World Program

App.js is the main Entry Point(if you've used "--template blank" while creating the app) Replace the existing Code in App.js with the following Code:

```bash
import { StatusBar } from 'expo-status-bar';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Hello World</Text>
      <StatusBar style="auto" />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```
> ### ***Instead of using `npx create-expo-app --template blank` we can use `npx create-expo-app` and clear unwanted code using `npm run reset-project` which leaves us with app folder structure which is used for routing different screens.***

## File-based Routing
- Each folder in the app folder corresponds to a route if it contains "**index.tsx**" and "**_layout.tsx**" files.
- The app folder corresponds to "**/**".

![Screenshot 2024-11-06 191937](https://github.com/user-attachments/assets/390d406b-f8bf-43e8-8471-6fe78be9f3b7)

- For example, a folder named "settings" with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/settings".
![Screenshot 2024-11-06 192034](https://github.com/user-attachments/assets/66a0a01e-414d-4993-bdd7-945e1c421031)

- A folder named "sub" inside "settings" folder with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/settings/sub".
- We can use files directly instead of folders. The name of the file with **.jsx** or **.tsx** files will correspond to new route.
![Screenshot 2024-11-06 192954](https://github.com/user-attachments/assets/27193272-9be9-42d5-8409-f810273e3e70)

- **_layout.tsx** is used to define shared UI elements such as headers, tab bars so that they persist between different routes.

>*The above code goes into the index file of whichever screen required.*

## Connecting Routes
- Using **Stack** of **expo-router** we can inter-link the screens of the application.
In the file **app/__layout.tsx**:
```typescript
import {Stack} from 'expo-router';
export default function Layout(){
  return (
    <Stack>
      <Stack.Screen name="index"/>
      <Stack.Screen name="details"/>
    </Stack>
  );
}
```
We can create a link element in **app/index.tsx** to link "/details" with root screen.
```typescript
<Link href={{ pathname: 'details'}}>Go to Details</Link>
```
> This creates stack for "/" and "/details".
