# angular-getterandsetter

employee-component.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-employee-component',
  templateUrl: './employee-component.component.html',
  styleUrls: ['./employee-component.component.css']
})
export class EmployeeComponentComponent implements OnInit {
  constructor() {}

  ngOnInit() {
    this.listFilter = 'Patel';
  }

  private _listFilter: string = '';

  get listFilter(): string {
    return this._listFilter;
  }

  set listFilter(value: string) {
    this._listFilter = value;
    console.log('In Setter:', value);
  }
}
```
employee-component.component.html

```html
<div>
<div>
  <input type="text" [(ngModel)]="listFilter" />
</div>
<br />
<div>
  Filter By: {{listFilter}}
</div>
</div>
```

app.module.ts

```js
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';

import { AppComponent } from './app.component';
import { employeeComponentComponent } from './employee-component/employee-component.component';

@NgModule({
  imports: [BrowserModule, FormsModule],
  declarations: [AppComponent, employeeComponentComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

app.component.html

```html
<app-employee-component></app-employee-component>
```


