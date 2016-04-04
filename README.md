# Deco Components

Deco Components are templates and dependencies that can be downloaded and inserted into your project through the Deco IDE.

### Contributing Components

Want to add components to Deco?

Please submit a pull request which adds your component(s) to the `package.json`, follow the format as described below.

For now, we'll review every component to make sure it works as expected in Deco. We plan to expand on the format and make the "registry" more scalable moving forward :)

### Format

```javascript
{
  // (String) Component name
  "name": "Activity Indicator IOS",

  // (String) Component publisher
  "publisher": "deco",

  // (String) Semver string of the component schema
  "schemaVersion": "0.0.1",

  // (String[]) Searchable tags
  "tags": ["core", "ui", "react-native"],

  // (String) Image to display in the insert menu
  "thumbnail": "https://placehold.it/100/100",

  // (String) A brief description
  "description": "A React Native component",

  // (Object) Metadata for the property inspector
  "inspector": {

    // (String) Automatically group properties - can be overriden individually
    "group": "ACTIVITY INDICATOR IOS"

  },

  // (Object) Where to find the component's text/metadata
  "template": {

    // (String) URL or relative path to the component's text
    "text": "https://rawgit.com/dabbott/deco-packages-test/master/core/ActivityIndicatorIOS.jsx",

    // (String) URL or relative path to the component's metadata
    "metadata": "https://rawgit.com/dabbott/deco-packages-test/master/.deco/core/ActivityIndicatorIOS.jsx.deco"
  },

  // (Object) Imports to insert at the top of the file
  "imports": {

    // (String|String[]|Object)
    // => import React from "react-native"
    "react-native": "React",

    // (String|String[]|Object)
    // => import { ActivityIndicatorIOS } from "react-native"
    "react-native": [
      "ActivityIndicatorIOS"
    ],

    // (String|String[]|Object)
    // => import React, * as R, { View, Text as T } from "react-native"
    "react-native": {
      default: 'React',
      star: true,
      alias: 'R',
      members: [
        'View',
        {
          name: 'Text',
          alias: 'T'
        }
      ]
    }
  },

  // (Object) Dependencies to install
  "dependencies": {

    // (String) Will run `npm install react-native --save`
    "react-native": "*"
  },
}
```

