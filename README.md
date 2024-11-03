#React Native 101
This is a brief walkthrough to build your own apps using **react native** for **IOS** and **Android**.
---

##Setting Up Environment

###**Expo Router**
It is an cross platform environment that enables developers to build apps for IOS and Android at the same time and run them on either of the platforms buy just downloading an app in the device and scanning a QR code.

-Open ==Command Prompt==
-Enter `npx expo install expo-router react-native-safe-area-context react-native-screens expo-linking expo-constants expo-status-bar`
-Navigate to the folder in which you want to build the app(using **cd FOLDERNAME**).
-Enter `npx create-expo-app@latest` to create the app(a new folder is created with the app name you've given).
-Enter `npx expo start` to run the app.
-To remove the existing boilerplate code use `npm run reset-project`.

*Open the .jsx or .tsx files in code editor.*

##Fundamentals

The source code of the app is present in "**app**" folder. **Expo Router** uses folders containing code inside the app folder to create routes inside the app.

###File-based routing
- Each folder in the app folder corresponds to a route if it contains "**index.tsx**" and "**_layout.tsx**" files.
- The app folder corresponds to "**/**"
- For example, a folder named "main" with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/main".
- A folder named "sub" inside "main" folder with "**index.tsx**" and "**_layout.tsx**" files corresponds to the route "/main/sub".
-**_layout.tsx** is used to define shared UI elements such as headers, tab bars so that they persist between different routes

###Hello World
*The code in the "**index.tsx**" file is for the respective screen(route).*

-**<View></View>** is a react native component for displaying UI elements(similar to a div in html).
-**<Text></Text>** is a react native component for displaying text.

`import { Text, View } from "react-native";

export default function Index() {
  return (
    <View>
      <Text>Hello World</Text>
    </View>
  );
}`