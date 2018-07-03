# Typescript React Native Set-Up Demo

In your terminal, cd into your project folder of choice and type in 
```exp init typescript-react-native-app```

We will need two dependencies and in order to install it you have to open up your ```package.json``` file and add the following

```"name": "typescript-react-native-app",```

```"version": "1.0.0",```

So your ```package.json``` should look like this:

```
{
  "name": "typescript-react-native-app",
  "version": "1.0.0",
  "main": "node_modules/expo/AppEntry.js",
  "private": true,
  "dependencies": {
    "expo": "^28.0.0",
    "react": "16.3.1",
    "react-native": "https://github.com/expo/react-native/archive/sdk-28.0.0.tar.gz"
  }
}
```

In your root folder of your project file you will need to: 

```yarn add -D react-native-typescript-transformer typescript```

After that is finished you will need to open up your ```app.json``` in your root folder and add:

```
"packagerOpts": {
  "sourceExts": [
    "ts",
    "tsx"
  ],
  "transformer": "node_modules/react-native-typescript-transformer/index.js"
  }
}
```

So your ```app.json folder should look like this:

```
{
  "expo": {
    "name": "typescript-react-native-app",
    "description": "This project is really great.",
    "slug": "typescript-react-native-app",
    "privacy": "public",
    "sdkVersion": "28.0.0",
    "platforms": ["ios", "android"],
    "version": "1.0.0",
    "orientation": "portrait",
    "icon": "./assets/icon.png",
    "splash": {
      "image": "./assets/splash.png",
      "resizeMode": "contain",
      "backgroundColor": "#ffffff"
    },
    "updates": {
      "fallbackToCacheTimeout": 0
    },
    "assetBundlePatterns": [
      "**/*"
    ],
    "ios": {
      "supportsTablet": true
    },
    "packagerOpts": {
      "sourceExts": [
        "ts",
        "tsx"
      ],
      "transformer": "node_modules/react-native-typescript-transformer/index.js"
      }
    }
}

```

The next step is to change the extensions for your ```App.js``` file to ```App.ts```

```
mv App.js App.tsx
```

Open up your ```App.tsx``` file and change your react import into:

```
import * as React from 'react';
```

Next in our terminal we will initialize the tsx file with: 
```
npx tsc --init
```

Open up the the ```tsconfig.json``` that was created from ```npx tsc --init``` and change your ```jsx: "preserve"``` too ```jsx: "react-native"``` 

Next, we will open up our ```package.json``` folder and add these two scripts:
```
"scripts": {
  "start": "exp start",
  "ios": "exp ios",
  "android": "exp android"
}
```

So your ```package.json``` will look like this:

```
{
  "name": "typescript-react-native-app",
  "version": "1.0.0",
  "main": "node_modules/expo/AppEntry.js",
  "private": true,
  "dependencies": {
    "expo": "^28.0.0",
    "react": "16.3.1",
    "react-native": "https://github.com/expo/react-native/archive/sdk-28.0.0.tar.gz"
  },
  "devDependencies": {
    "react-native-typescript-transformer": "^1.2.10",
    "typescript": "^2.9.2"
  },
  "scripts": {
    "start": "exp start",
    "ios": "exp ios",
    "android": "exp android"
  }
}

```

Next