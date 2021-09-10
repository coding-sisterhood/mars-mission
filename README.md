# mars-mission

Instructions for building a React application that shows photos gathered by NASA’s Curiosity, Opportunity, and Spirit rovers on Mars.

To succeed in our Mars Mission, we need to:

- create ReactJS application
- fetch the data from public NASA api
- display the latest available photo of Mars.

### Requirements

- latest NodeJS LT version (>= 10.16)
- latest package manager, such as `yarn` or `npm`
- your choice of code editor (Visual Studio Code is highly recommended)

### Assumptions

For this mission, we will assume that you will have the following knowledge:

- basic JavaScript
- basic use of terminal/command prompt
- a few standard programming concepts such as states, variables, functions

## Step 1: create a ReactJS application by using create-react-app template

To create a project called mars-mission, run this command in your terminal:

`npx create-react-app mars-mission`

Navigate to the application’s root folder and run

`npm install` or `yarn install`

to install all the packages.

Run

`npm start` or `yarn start`

to start your project in the localhost. When you open `http://localhost:3000/` now you can see a default page with animated image.

## Step 2: create local state to store NASA data

Import `useState` hook in the App.js file:

`import { useState } from 'react';`

Inside the App function, define the state:

`const [data, setData] = useState(undefined);`

## Step 3: fetch the data for your mission

Install `axios` by running

`yarn add axios`

in the root application's folder.

Import `useEffect` hook and `axios` in the App.js file:

`import { useState, useEffect } from 'react';`
`import axios from 'axios';`

Inside the App function, add the below code to it:

```
useEffect(() => {
    axios.get(`https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?earth_date=2021-8-30&api_key=DEMO_KEY`)
    .then(response => {
      console.log(response);
      const marsData = response.data.photos;
      setData(marsData);
    })
  }, []);
```

If you add

`console.log('data', data);`

in your App function before the return statement, you'll see that `data` now is an array of items containing information about the photos made on 2021-8-30

## Step 4: display the latest photo from Mars

In App.js, before the return statement, define a variable to get a url of the most recent photo:

```
const mostRecentPhotoUrl = data ? data[data.length - 1].img_src : '';
```

Inside the return statement, delete everything and instead add the below code:

```
<img src={mostRecentPhotoUrl} />
```

If you check your localhost now, you may see a beautiful Mars landscape. If you see an error instead, here is the result code of App.js for you to compare with what you've got:

```
import './App.css';
import { useState, useEffect } from 'react';
import axios from 'axios';

function App() {
  const [data, setData] = useState(undefined);

  useEffect(() => {
    axios.get(`https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?earth_date=2021-8-30&api_key=DEMO_KEY`)
    .then(response => {
      console.log(response);
      const marsData = response.data.photos;
      setData(marsData);
    })
  }, []);

  const mostRecentPhotoUrl = data ? data[data.length - 1].img_src : '';

  return (
    <img src={mostRecentPhotoUrl} />
  );
}

export default App;
```

## Congrats, Mars Mission is complete!

## Extra challenges

### Create a child component

Add a child component called Picture that gets the data from App component through the props and returns the picture

### Show more data

Add a section to the Picture component to display the rest of the data (date, rover's name etc.)

## Useful links

[ReactJS official documentation](https://reactjs.org/)

[create-react-app official documentation](https://create-react-app.dev/)

[NASA public APIs](https://api.nasa.gov/)

## this is to test github cli
