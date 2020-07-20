# react-native-styling

## Customize Styling

- There no css in react-native we use javascript to style our code.
- You have two ways to style an element:

1. Inside the tag itself like

   ```javascript
   <View style={{ width: 100, height: 100, backgroundColor: "blue" }} />
   ```

2. Use StyleSheet

   ```javascript
   // don't forget to import StyleSheet
   import { StyleSheet } from "react-native";

   export default App = () => (
     // call your style sheet
     <View style={styles.container}>
       <Text>hello from react Native</Text>
     </View>
   );

   // create StyleSheet
   const styles = StyleSheet.create({
     container: {
       flex: 1,
       backgroundColor: "white",
       alignItems: "center",
       justifyContent: "center",
       paddingTop: Platform.OS === "android" ? StatusBar.CurrentHeight : 0,
     },
   });
   ```

   you can pass more than one style by nesting all styles in an array like:

   ```javascript
   <View style={[styles.container ,styles.formContainer]}>
   ```

   ##### When you call multiple styles the right one will override the left one .

   It's recommended to use StyleSheet for many reasons:

   1. By moving styles away from the render function, you're making the code easier to understand.

   2. Naming the styles is a good way to add meaning to the low level components in the render function.

   3. Making a stylesheet from a style object makes it possible to refer to it by ID instead of creating a new style object every time.

   4. It also allows to send the style only once through the bridge. All subsequent uses are going to refer an id (not implemented yet).
   
   5. StyleSheet check your syntax and throw an error when you have something wrong in you style.

      [source](https://stackoverflow.com/questions/38958888/react-native-what-is-the-benefit-of-using-stylesheet-vs-a-plain-object#:~:text=Performance%3A,only%20once%20through%20the%20bridge.)

## Dimensions in react-native

look at this example:

```javascript
<View style={{ width: 150, height: 150 }} />
```

What is the dimensions used in react-native?

- in react-native we use "DIP" = Density-Independent-pixel , so in our example width and height are 100 dips, and the actual size on the mobile will be 100 x Scale Factor.

  ![pids vs pixel](https://i.ibb.co/4t3Thsg/Annotation-2020-07-20-192607.png)

- use [Dimension](https://reactnative.dev/docs/dimensions) or [useWindowDimension](https://reactnative.dev/docs/usewindowdimensions) to know the exact dimension of your mobile screen.

## Flexbox

> Flexbox works the same way in React Native as it does in CSS on the web, with a few exceptions. The defaults are different, with flexDirection defaulting to column instead of row, and the flex parameter only supporting a single number.
>
> [react-native docs](https://reactnative.dev/docs/flexbox)

#### flex property

We use flex property to specify how the item grow to fill the available space.

```
<View style={{styles.container}}>
  <View style={backGroundColor:'tomato', flex:1}>
  <View style={backGroundColor:'gold', flex:2}>
  <View style={backGroundColor:'greenyellow ', flex:3}>
<View>
```

![flex](https://cdn-images-1.medium.com/max/800/1*PhCFmO5tYX_sZSyCd4vO3w.png)

- [flexbox docs](https://reactnative.dev/docs/flexbox)

## Position

it's like regular css, but the default position is 'relative'

## [Platform Specific Code](https://reactnative.dev/docs/platform-specific-code)

## [exercise](https://programmingwithmosh.com/wp-content/uploads/2020/05/Layout-Exercises.pdf)
