- yarn.lock vs proj folder

https://marmelab.com/react-admin/Tutorial.html

- The App component renders an ```<Admin>``` component, which is the root component of a react-admin application. 
  - This component expects a dataProvider prop - a function capable of fetching data from an API. 

- The ```<Admin>``` component expects one or more ```<Resource>``` child components. Each resource maps a name to an endpoint in the API.
- ```<Resource>``` also defines the React components to use for each CRUD operation (list, create, edit, and show).
- The ra-data-json-server data provider translates these actions to a query string that JSONPlaceholder understands.
- React-admin relies on material-ui, a set of React components modeled after Google’s Material Design UI Guidelines. Material-ui uses JSS, a CSS-in-JS solution, for styling components. 
- From a UX point of view, fields containing large chunks of text should not appear in a Datagrid, only in detail views. 
- use the ```<EditGuesser>``` to help bootstrap it.
- Optimistic Rendering and Undo: 5 sec delay
- Filters are “search-as-you-type”, meaning that when the user enters new values in the filter form, the list refreshes (via an API request) immediately.
- mobile
```js
const isSmall = useMediaQuery(theme => theme.breakpoints.down('sm'));
```
- React-admin delegates every data query to a Data Provider object, which acts as an adapter to your API.
- It’s the Data Provider’s job to emit HTTP requests and transform the response into the format expected by react-admin.
