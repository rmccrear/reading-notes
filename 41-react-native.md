# React Native

## Core Components

Core Components in React Native correspond to Components in a Component Library for React like ReactStrap or MUI. The difference is that you can't use html components in React Native to supplement them. A few of the most common components are `<View>` (and `<ScrollView>`), `<Text>`, `<Image>`, and `<TextInput>`. Most of the components you might miss from html are implemented as Core Components. Some, like `<ScrollView>` or `<FlatList>` are important to provide a mobile feel. You can browse the Core Components to get a feel for what you might like to use in your app.

## Expo

Expo is an easy way to get started building a mobile app in React Native. You could say it is a little like Heroku was for web development, but Expo is for mobile development. It can get you started with `create-expo-app` which is a lot like `create-react-app`. It will like to your code base like Heroku does, and you can deploy to expo from your git repository.

Expo can be tricky to setup, even if the docs make it appear easy. As I write this, `create-expo-app` fails with node-v18, but works fine with node-v16. So be sure to use the node version with lts.

## Expo Snack

If Expo is like Heroku for mobile apps, then Expo Snack is like Repl.it or Codesandbox.io. It lets you work in a browser and preview on the phone. It's a great way to get a ...errmm... taste of what React Native will be like.

## Ejecting

Just as you can "eject" from create-react-app, you can "eject" from create-expo-app. Then it will be up to you to manage the build process.

_ExpoKit, which is required for ejecting is depreciated. You can still use React Native outside of Expo, but you will need to use the bare workflow to do so going forward._
