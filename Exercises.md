# Workshop React Native with Expo

## Step 0: Installation

All the installation required to do the exercises are detailed in the [SETUP](./README.md)

## Step 1: `TopBar` component

In `App.tsx`, create a component that will display the title of the app (which manage also the status bar).

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

You should just call the component `ListCoins` and provide him the data in your `app` component.

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

- `dataCoins` is a const variable but you can change its value with `setDataCoins` 
- `dataCoins` is an array of objects

TIPS:

You should take a look to the [map](https://reactjs.org/docs/lists-and-keys.html) function.

## Step 3: function `addCoinToList`

Now try to create a method `addCoinToList` who can add a coin to the list when you click on the button 'Add coin'. You should create two inputs (one for the type and one for the value).

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

If you add too many coins, can you see them all ? Maybe with a [ScrollView](https://docs.expo.io/versions/latest/react-native/scrollview/) it will be better.

## Step 5 : AsyncStorage

You must have noticed that if we restart the application, we lose all the data. So find a way to save the data when adding a coin to the list and restore the data when launching the application.

You will find all the information you need to complete this exercise on this [page](https://reactnative.dev/docs/asyncstorage).

## Last step : Get data from an API

Many mobile apps need to get some resources from a API. In our case, we will use this [API](https://www.coinapi.io). You will need to register on this site to get a free API Key.

When you add a coin, you must use the USD price(`price_usd`) given by the API (of the chosen coin) to calculate the final price. You should take a look at the [doc](https://docs.coinapi.io/#list-all-assets) of the API to see how to get data from it.

Here is the [fetch](https://docs.expo.io/versions/v37.0.0/react-native/network/) method in react native to get data from an API. The method we will use in this exercise is the `GET` method.

For example, the API will return a list of object :

```tsx
Object {
  "asset_id": "BTC",
  "data_end": "2020-11-16",
  "data_orderbook_end": "2020-08-05T14:38:38.3413202Z",
  "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",
  "data_quote_end": "2020-11-16T20:37:47.8273198Z",
  "data_quote_start": "2014-02-24T17:43:05.0000000Z",
  "data_start": "2010-07-17",
  "data_symbols_count": 42764,
  "data_trade_end": "2020-11-16T20:38:42.2880000Z",
  "data_trade_start": "2010-07-17T23:09:17.0000000Z",
  "id_icon": "4caf2b16-a017-4e26-a348-2cea69c34cba",
  "name": "Bitcoin",
  "price_usd": 16832.032529778964,
  "type_is_crypto": 1,
  "volume_1day_usd": 81929387601293.88,
  "volume_1hrs_usd": 2096688224434.68,
  "volume_1mth_usd": 5001061786606472,
},
Object {
  ...
  ...
}
```

In order to calculate the purchase price of a coin, you will need to divide the input value by the price in USD of the chosen coin.

## Bonus

You're done ? Congratulation! Now add a select menu for all the coin given by the API. It will be way better than just an text input to add a coin.
The power of react native? It has plenty of modules ready to use 😉

## Authors

- [Camille Samson](https://github.com/Samson-Git)
