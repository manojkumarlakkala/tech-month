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

## File-based Routing
- Each folder in the app folder corresponds to a route if it contains "**index.tsx**" and "**_layout.tsx**" files.
- The app folder corresponds to "**/**"
![Screenshot 2024-11-06 191937](https://github.com/user-attachments/assets/390d406b-f8bf-43e8-8471-6fe78be9f3b7)

- For example, a folder named "settings" with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/settings".
![Screenshot 2024-11-06 191853](https://github.com/user-attachments/assets/63dd7bd4-a4af-454a-a44a-6fd9ed08f133)

- A folder named "sub" inside "settings" folder with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/settings/sub".
- We can use files directly instead of folders. The name of the file with **.jsx** or **.tsx** files will correspond to new route.
![Screenshot 2024-11-06 192954](https://github.com/user-attachments/assets/27193272-9be9-42d5-8409-f810273e3e70)

- **_layout.tsx** is used to define shared UI elements such as headers, tab bars so that they persist between different routes.
