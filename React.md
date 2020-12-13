
- index.js
```js
ReactDOM.render(<App/>, document.getElementById('root'));

export default App;

{var}

this.toggleDisplayBio = this.toggleDisplayBio.bind(this);
```
- Component
- JSX: tag
  - React.createElement()
- bind
- state
  - Never  directly modify state
  - setState retrigger render()
- props

- Bundling is the process of taking many JavaScript files and combining them into one giant JavaScript file for the html to refer to. This is useful because the browser doesn’t natively support the import/export system that is used in React projects.
  - Parcel-bundler is a tool that achieves bundling.

- Transpiling is the process of translating modern JavaScript code into a syntax that the browser actually supports. This is necessary because, as the JavaScript language evolves and adds new features, the browser must keep up and support those additions. Therefore, the feature set that the browser can support will always be a bit behind the overall JavaScript language.
  - Babel is a tool that achieves transpilation.

