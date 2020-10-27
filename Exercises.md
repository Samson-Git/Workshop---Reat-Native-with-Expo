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

- `dataCoins` is a const variable but you can change his value with `setTaskList` 
- `dataCoins` is an array of objects

TIPS:

You should take a look to the [map](https://reactjs.org/docs/lists-and-keys.html) function.


## Authors
- [Camille Samson](https://github.com/Samson-Git)
