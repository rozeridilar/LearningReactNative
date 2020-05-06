# Learning React Native ⚡️
Hello there, I am so new to React Native Development, and would like to share all my notes here!

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
