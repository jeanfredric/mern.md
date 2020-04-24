## Redux setup

* Skapa mappen `reducers` i `/client/src` och skapa filen `index.js`. 

* Backa ut till `/client/src` och skapa filen `store.js` kod:
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
* Denna fil kommer vi inte att behöva röra igen
* Klistra ihop React och Redux genom att skriva följande kod i `app.js`:
```javascript
import { Provider } from 'react-redux';
import store from './store';
```
* Wrappa sedan hela app-funktionen i `app.js` med taggen `<Provider store={store}> ... </Provider>`

* Addera sedan följande kod till `index.js`:
```javascript
import { combineReducers } from 'redux';
import auth from './auth';
import profile from './profile';

export default combineReducers({ auth, profile });
```
* I filen ovan har två reducers lagts till (auth och profile). Addera varje reducer som du skapar.

* Nu ska det fungera om du går in i Chrome och klickar igång Redux DevTools.
