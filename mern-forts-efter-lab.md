## Redux setup

Skapa mappen `reducers` i client/src och skapa filen `index.js` i mappen och skriv följande kod i `index.js`:
```javascript

import { createStore, applyMiddleware } from 'redux';
import { composeWithDevTools } from 'redux-devtools-extension';
import thunk from 'redux-thunk';
import rootReducer from './reducers/index';

//empty object
const initialState = {};

const middleware = [thunk];

//apply middlewarestore
const store = createStore(
	rootReducer,
	initialState,
	composeWithDevTools(applyMiddleware(...middleware))
);

export default store;
```

