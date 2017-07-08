# React Native Everywhere Image Picker
Cross-platform image picker for React/React Native. Built for iOS, Android, and web.

#### web screenshots

![](https://github.com/mini-eggs/react-native-everywhere-image-picker/raw/master/artwork/web-example.png)

#### iOS screenshots

![](https://github.com/mini-eggs/react-native-everywhere-image-picker/raw/master/artwork/ios-example.png)

#### Installation
`npm install --save react-native-everywhere-image-picker`

#### Requirements
1. For web use in `create-react-app` you MUST have `react-scripts` version 1.0.8 or higher.

#### example
```javascript
import React from "react";
import { Text, Image, View } from "react-native";
import ImagePicker from "react-native-everywhere-image-picker";

const style = {
  container: {
    flex: 1,
    alignItems: "center",
    justifyContent: "center"
  },
  image: {
    width: 200,
    height: 200,
    marginTop: 25
  }
};

export default class Example extends React.Component {
  state = { uri: null };

  _handleImage = ({ uri }) => {
    this.setState(() => ({ uri }));
  };

  _handleFail = ({ error }) => {
    console.log(error);
  };

  render() {
    return (
      <View style={style.container}>
        <ImagePicker onComplete={this._handleImage} onFail={this._handleFail}>
          <Text>Pick an image from camera roll</Text>
        </ImagePicker>
        {this.state.uri &&
          <Image source={{ uri: this.state.uri }} style={style.image} />}
      </View>
    );
  }
}
```
