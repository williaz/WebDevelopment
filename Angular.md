### @ViewChild
- a Property decorator to bind view DOM to fields in @Component or @Directive
- query is set before ngAfterViewInit
- selector property: template ref (variable)

### [Get ag-grid Grid api](https://www.ag-grid.com/angular-data-grid/grid-interface/)
- get from onGridReady event
- query with @ViewChild
```js
<ag-grid-angular
    #myGrid // assign an angular ID to the grid - optional

    // provide gridReady callback to the grid
    (gridReady)="onGridReady($event)"
    // ...
 />

 // in onGridReady, store the api for later use
 onGridReady = (params) => {
     this.api = params.api;
     this.columnApi = params.columnApi;
 }
 @ViewChild('myGrid') grid!: AgGridAngular;
```
### [HttpClient POST](https://www.concretepage.com/angular/angular-httpclient-post)
- header, responseType as options

```js

createArticle(article: Article): Observable<Article> {
  let httpHeaders = new HttpHeaders({
	'Content-Type' : 'application/json',
	'Cache-Control': 'no-cache'
     });    
     let options = {
	       headers: httpHeaders,
         observe: 'response',
         responseType: 'blob'
     };        
     return this.http.post<Article>(this.url, JSON.stringify(article), options);
} 


post(url: string, body: any | null, options: {
    headers?: HttpHeaders | {
        [header: string]: string | string[];
    };
    observe?: HttpObserve;
    params?: HttpParams | {
        [param: string]: string | string[];
    };
    reportProgress?: boolean;
    responseType?: 'arraybuffer' | 'blob' | 'json' | 'text';
    withCredentials?: boolean;
} = {}): Observable<any> 
```

### [JSON parse & stringify](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)
```js
const json = '{"result":true, "count":42}';
const obj = JSON.parse(json);

console.log(JSON.stringify({ x: 5, y: 6 }));
// Expected output: '{"x":5,"y":6}'
```








