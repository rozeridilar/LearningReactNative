# Learning React Native ⚡️
Hello there, I am so new to React Native Development, and would like to share all my notes here!
<strong>The IDE</strong>
I am still struggling with finding the best ide and extensions, since I come from a swift background these all so new to me! However I found great recommendations in below links that helped me a quite a lot:

https://medium.com/react-native-training/vscode-for-react-native-526ec4a368ce

https://hackernoon.com/10-essential-vs-code-extensions-for-javascript-developers-in-2019-e8320e3f421e

https://medium.com/hackernoon/vs-code-extensions-for-happier-javascript-coding-e258f72dd9c1

The essentials for me are React Native Tools, Babel JavaScript, Import Cost, ESLint, Prettier, Flow Language Support, ES7 React snippets, bracket colorizer, TODO Highlight and indent rainbows.

Lets dive into fundementals!

<strong>Working with Content</strong>

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
