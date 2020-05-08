# Learning React Native ⚡️
Hello there, I am so new to React Native Development, and would like to share all my notes here!

## #1 The IDE
I am still struggling with finding the best ide and extensions, since I come from a swift background these all so new to me! However I found great recommendations in below links that helped me a quite a lot:

https://medium.com/react-native-training/vscode-for-react-native-526ec4a368ce

https://hackernoon.com/10-essential-vs-code-extensions-for-javascript-developers-in-2019-e8320e3f421e

https://medium.com/hackernoon/vs-code-extensions-for-happier-javascript-coding-e258f72dd9c1

The essentials for me are React Native Tools, Babel JavaScript, Import Cost, ESLint, Prettier, Flow Language Support, ES7 React snippets, bracket colorizer, TODO Highlight and indent rainbows.

Lets dive into fundementals!

## #2 Working with Content

Rules of JSX: 
- We can assemble different JSX elements like normal HTML.
- We configure different JSX elements using 'props'.
- We can refer to JS variables inside of a JSX blocks by using curly braces.
- We can assign JSX elements to a variable, then show that variable inside of a JSX block.

```javascript
const ComponentsScreen = () => {
  const helloMsg = { message: "Hi there!" };
  const greeting = (
    <View>
      <Text style={styles.textStyle}>This is the ComponentsScreen.</Text>
      <Text>{helloMsg.message}</Text>
    </View>
  );
  return greeting;
};

const styles = StyleSheet.create({
  textStyle: {
    fontSize: 30,
  },
});

```

## #3 FlatList

As I understand, flatlist kind of acts like a recycler view in android. The FlatList component displays the similar structured data in a scrollable list. It works well for large lists of data where the number of list items might change over time. The FlatList shows only those renders elements which are currently displaying on the screen, not all the elements of the list at once.

The FlatList component takes two required props: data and renderItem. Also it needs keyExtractor props for key value pairing.

The data is the source of elements for the list, and renderItem takes one item from the source and returns a formatted component to render.

List Screen: 
```javascript
const ListScreen = () => {
  const friends = [new Friend("Friend #1", 22), new Friend("Friend #2", 23)];
  return (
    <FlatList
      keyExtractor={(friend) => friend.name}
      data={friends}
      renderItem={(element) => {
        const name = element.item.name;
        const age = element.item.age;
        console.log(element);
        return (
          <Text style={styles.textStyle}>
            {name} - Age {age}
          </Text>
        );
      }}
    />
  );
};

const styles = StyleSheet.create({
  textStyle: {
    marginVertical: 50,
  },
});
```
Friend Model: 
```javascript
export default class Friend {
  name: string;
  age: int;
  constructor(name: string, age: int) {
    this.name = name;
    this.age = age;
  }
}
```

Question: How can I put friends list as a parameter in the listscreen const, rather than a inner variable?

## #4 Building Reusable Components
Component with Image and Text 
```javascript
const ImageDetail = ({ imageScore, title, imageSource }) => {
  return (
    <View>
      <Image source={imageSource} />
      <Text>{title}</Text>
      <Text>Image Score - {imageScore}</Text>
    </View>
  );
};
```
As I understand, this one is more like a ui view components like in swift. Assume you need to create your custom button like with a rounded corner radius, with shade and you get to use that button several times in your app. So in that case it is always better to create your custom button as a UI Component in swift. This Building Reusable Components is the same meaning in react-native. 

Here we have a custom Image Component with image title, image score and source. We use the 'props' <strong> to communicate data from a parent to a child. </strong> Above example, instead getting props directly we added the parameters we need from props.

## #5 State Management

State tracks a single piece of data and any time it changes, it will update the UI.

```javascript
const CounterScreen = () => {
  //Array destructring
  const [counter, setCounter] = useState(0);
  return (
    <View>
      <View style={styles.viewStyle}></View>
      <Button
        title="Increase"
        onPress={() => {
          setCounter(counter + 1);
          console.log(counter);
        }}
      />

      <View style={styles.viewStyle}></View>

      <Button
        title="Decrease"
        onPress={() => {
          setCounter(counter - 1);
          console.log(counter);
        }}
      />
      <View style={styles.viewStyle}></View>

      <Text style={styles.headline}> Current Count: {counter}</Text>
    </View>
  );
};
```
Above, there is a counter variable that changes by useState, once the `setCounter()` function is triggered react native updates the whole view. 
