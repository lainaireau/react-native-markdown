# react-native-markdown

A component for rendering Markdown in React Native. Pull requests are really appreciated.

## Known issues

- Due to [a bug](https://github.com/facebook/react-native/issues/824) in underlying layout engine for React Native ([facebook/css-layout](https://github.com/facebook/css-layout)), this module will put your application in an infinite loop unless you patch the upstream changes from `css-layout`'s' `Layout.c` and `Layout.h` files.

## Getting started

1. add this line to your package.json `dependencies`

    `"react-native-simple-markdown": "git+https://github.com/andangrd/react-native-markdown.git"`
    
2. run `npm install`

## Usage

All you need is to `import` the `react-native-simple-markdown` module and then use the
`<Markdown/>` tag.

```javascript
import { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  View
} from 'react-native';
import Markdown from 'react-native-simple-markdown';

class mdApp extends Component {
  render() {
    return (
      <View>
        <Markdown >
          # This is Heading 1
          ## This is Heading 2
          1. List1 {'\n'}
          2. List2 {'\n'} 
          {'\t'}1. sublist1{'\n'}
          {'\t'}description sublist1.{'\n'}
          {'\t'}2. sublist2{'\t\t'}{'\n'}
          * List3{'\n'}
          * List4{'\n'}
          {'\t'}1. **bold text** {'\n'}
          {'\t'}2. this line contain * and should not be a new sublist{'\t\t'}{'\n'}
          5.  Last list{'\n\n'}
          Some *really* basic **Markdown**.
          {'\n\n'}
          | # | Name   | Age |{'\n'}
          |---|--------|-----|{'\n'}
          | 1 | John   | 19  |{'\n'}
          | 2 | Sally  | 18  |{'\n'}
          | 3 | Stream | 20  |{'\n'}
        </Markdown >
      </View>
    );
  }
});

AppRegistry.registerComponent('mdApp', () => mdApp);
```

## Properties

#### `style`

Default style properties will be applied to the markdown. You will likely want to customize these styles, the following properties can be used to modify the rendered elements:

*Note: The text inside the parentheses denotes the element type.*

- `autolink` (`<Text>`) - WIP
- `blockQuote` (`<Text>`) - WIP
- `br` (`<Text>`)
- `codeBlock` (`<View>`) - WIP
- `del` (`<Text>`)
- `em` (`<Text>`)
- `heading` (`<Text>`) - Also `heading1` through `heading6`
- `hr` (`<View>`)
- `image` (`<Image>`) - Implemented but size is fixed to `50x50` until auto width is supported by React Native.
- `inlineCode` (`<Text>`)
- `link` (`<Text>`) - WIP
- `list` (`<View>`) - Also `sublist` (`<View>`), `listItem` (`<View>`), `listItemBullet` (`<Text>`) and `listItemNumber` (`<Text>`)
- `sublist` (`<View`) - Also `listItem` (`<View>`), `listItemBullet` (`<Text>`) and `listItemNumber` (`<Text>`)
- `mailto` (`<Text>`) - WIP
- `newline` (`<Text>`) - WIP
- `paragraph` (`<View>`)
- `plainText` (`<Text>`) - Use for styling text without any associated styles
- `strong` (`<Text>`)
- `table` (`<View>`)
- `tableHeader` (`<View>`)
- `tableHeaderCell` (`<Text>`)
- `tableRow` (`<View>`)
- `tableRowCell` (`<View>`)
- `tableRowLast` (`<View>`, inherits from `tableRow`)
- `text` (`<Text>`) - Inherited by all text based elements
- `u` (`<View>`)
- `url` (`<Text>`)
- `view` (`<View>`) - This is the container `View` that the Markdown is rendered in.
