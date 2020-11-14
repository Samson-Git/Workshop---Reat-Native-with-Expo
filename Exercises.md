# Workshop React Native with Expo

## Step 0: Installation

All the installation required to do the exercises are detailed in the [SETUP](./README.md)

## Step 1: `TopBar` component

In `App.tsx`, create a component that will display the title of the app (who manage also the status bar).

The `title` must be received from the [props](https://docs.expo.io/versions/v37.0.0/react-native/props/) and be at the center of the view.

Example :

```tsx
function TopBar(props : any) {
  return (/* CONTENT */);
}
```

To display your `TopBar` component, paste this line in your app component:

```tsx 
<TopBar title="First App" ></TopBar>
```

TIPS:

For this exercice, you will need to change and add some css in the `StyleSheet`.
If you want to learn the basic, use this platform [FlexBox](https://flexboxfroggy.com)

You should also take a look at the constant variable available in [Expo](https://docs.expo.io/versions/latest/sdk/constants/). (Every status bar have the same height ?)

## Step 2: `ListCoins` component

Create a component that will display a list of coins.
Here is the data who need to be display :

```tsx
const [dataCoins, setDataCoins] = React.useState([{name: 'BTC', value: '10000'}, {name: 'ETH', value: '600'}]);
``` 

We should just call the component `ListCoins` and provide him the data in your `app` component.

Example:

```tsx
export default function App() {
  const [dataCoins, setDataCoins] = React.useState([{name: 'BTC', value: '10000'}, {name: 'ETH', value: '600'}]);

  return (
      <View style={styles.container}>
        <TopBar title="First App" ></TopBar>
        <ListCoins data={dataCoins}></ListCoins>
      </View>
  );
}
```

- `dataCoins` is a const variable but you can change his value with `setDataCoins` 
- `dataCoins` is an array of objects

TIPS:

You should take a look to the [map](https://reactjs.org/docs/lists-and-keys.html) function.

## Step 3: function `addCoinToList`

Now try to create a method `addCoinToList` who can add a coin to the list when you click on the button 'Add coin'. You should create two input (one for the type and one for the value).

Each input must be reset when you add a coin to the list.

Use TouchableOpacity for the button and TextInput for the input. Here is the import you should add: 

```tsx
  import { TouchableOpacity, TextInput} from 'react-native';
```

Exemple of TouchableOpacity : 

```tsx
  <TouchableOpacity
    onPress={ /* FUNCTION TO CALL */}
    style={ /* CSS STYLE */}>
      <Text>Add coin</Text>
  </TouchableOpacity>
```

TIPS:

If you add too many coin, can you see them all ? Maybe with a [ScrollView](https://docs.expo.io/versions/latest/react-native/scrollview/) it will be better.

## Last step : AsyncStorage

You must have noticed that if we restart the application, we lose all the data. So find a way to save the data when adding a coin to the list and restore the data when launching the application.

You will find all the information you need to complete this exercise on this [page](https://reactnative.dev/docs/asyncstorage).

## Authors
- [Camille Samson](https://github.com/Samson-Git)
