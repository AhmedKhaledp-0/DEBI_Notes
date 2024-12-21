# Bootstrap

> builtin components and `CSS` classes

- runs on all browser
- mobile first approach

# Table of Contents

- [Bootstrap](#bootstrap)
- [Table of Contents](#table-of-contents)
  - [How to use Bootstrap](#how-to-use-bootstrap)
  - [Breakpoints](#breakpoints)
  - [Overriding Bootstrap Properties](#overriding-bootstrap-properties)
  - [types of container](#types-of-container)
  - [Grid `col`](#grid-col)
  - [table](#table)
  - [table-striped](#table-striped)
  - [table-bordered](#table-bordered)
  - [table-hover](#table-hover)
  - [utilities](#utilities)
  - [table-responsive](#table-responsive)
  - [img](#img)
  - [carousel](#carousel)
  - [alerts](#alerts)
  - [Buttons](#buttons)
  - [Forms](#forms)
  - [Badges](#badges)
  - [Cards](#cards)
  - [Spinners](#spinners)
  - [Toasts](#toasts)
  - [Tooltips](#tooltips)

## How to use Bootstrap

- Download cdn files
- use online version

## Breakpoints

Bootstrap uses a series of breakpoints to determine how the layout should adjust at different screen sizes. The breakpoints are:

| Breakpoint        | Class Prefix | Dimensions |
| ----------------- | ------------ | ---------- |
| Extra small       |              | <576px     |
| Small             | `sm`         | ≥576px     |
| Medium            | `md`         | ≥768px     |
| Large             | `lg`         | ≥992px     |
| Extra large       | `xl`         | ≥1200px    |
| Extra extra large | `xxl`        | ≥1400px    |

## Overriding Bootstrap Properties

To override Bootstrap properties, you can use custom CSS. Make sure your custom CSS file is loaded after the Bootstrap CSS file.

```html
<link
  href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
  rel="stylesheet"
/>
<link href="custom.css" rel="stylesheet" />
```

In `custom.css`:

```css
/* Override Bootstrap properties */
.btn-primary {
  background-color: #ff5733;
  border-color: #ff5733;
}
```

## types of container

- `.container` have a `margin-right` and `margin-left`

- `.container-fluid`

  - A full-width container that spans the entire width of the viewport.

  ```html
  <div class="container-fluid">
    <h1>Full Width Container</h1>
    <p>This container spans the entire width of the viewport.</p>
  </div>
  ```

## Grid `col`

> `2D` structure

- Full width 12 column

  ```html
  <div class="container">
    <div class="row">
      <div class="col-md-4">Column 1</div>
      <div class="col-md-4">Column 2</div>
      <div class="col-md-4">Column 3</div>
    </div>
  </div>
  ```

## table

> Basic table structure

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

## table-striped

> Adds zebra-striping to any table row within the `<tbody>`.

```html
<table class="table table-striped">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Jane</td>
      <td>Smith</td>
      <td>@janesmith</td>
    </tr>
  </tbody>
</table>
```

## table-bordered

> Adds borders on all sides of the table and cells.

```html
<table class="table table-bordered">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

## table-hover

> Enables a hover state on table rows within a `<tbody>`.

```html
<table class="table table-hover">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Jane</td>
      <td>Smith</td>
      <td>@janesmith</td>
    </tr>
  </tbody>
</table>
```

## utilities

> `Active`: Adds a blue background color to the active table row or cell.

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr class="active">
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

> `Success`: Adds a green background color to the table row or cell.

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr class="success">
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

> `Info`: Adds a light blue background color to the table row or cell.

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr class="info">
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

> `Warning`: Adds a yellow background color to the table row or cell.

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr class="warning">
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

> `Danger`: Adds a red background color to the table row or cell.

```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr class="danger">
      <td>1</td>
      <td>John</td>
      <td>Doe</td>
      <td>@johndoe</td>
    </tr>
  </tbody>
</table>
```

## table-responsive

> Makes tables scroll horizontally on small devices `(under 768px)`.

```html
<div class="table-responsive">
  <table class="table">
    <thead>
      <tr>
        <th>#</th>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Username</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>John</td>
        <td>Doe</td>
        <td>@johndoe</td>
      </tr>
    </tbody>
  </table>
</div>
```

## img

> Responsive images that scale nicely to the parent element.

```html
<img src="path/to/image.jpg" class="img-responsive" alt="Responsive image" />
```

## carousel

> A slideshow component for cycling through elements.

```html
<div id="myCarousel" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
    <li data-target="#myCarousel" data-slide-to="1"></li>
    <li data-target="#myCarousel" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="item active">
      <img src="img1.jpg" alt="First slide" />
    </div>
    <div class="item">
      <img src="img2.jpg" alt="Second slide" />
    </div>
    <div class="item">
      <img src="img3.jpg" alt="Third slide" />
    </div>
  </div>
  <a class="left carousel-control" href="#myCarousel" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left"></span>
  </a>
  <a class="right carousel-control" href="#myCarousel" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right"></span>
  </a>
</div>
```

## alerts

> Provides contextual feedback messages for typical user actions.

```html
<div class="alert alert-success">
  <strong>Success!</strong> This is a success alert.
</div>
<div class="alert alert-info">
  <strong>Info!</strong> This is an info alert.
</div>
<div class="alert alert-warning">
  <strong>Warning!</strong> This is a warning alert.
</div>
<div class="alert alert-danger">
  <strong>Danger!</strong> This is a danger alert.
</div>
```

## Buttons

> Various button styles for different actions.

```html
<button type="button" class="btn btn-default">Default</button>
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-link">Link</button>
```

## Forms

Bootstrap provides a variety of form controls and layout options.

```html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input
      type="email"
      class="form-control"
      id="exampleInputEmail1"
      aria-describedby="emailHelp"
    />
    <div id="emailHelp" class="form-text">
      We'll never share your email with anyone else.
    </div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" />
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

## Badges

Badges are used to add additional information to any content.

```html
<h1>Example heading <span class="badge bg-secondary">New</span></h1>
```

## Cards

Cards are flexible content containers.

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="..." />
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## Spinners

Spinners indicate a loading state.

```html
<div class="spinner-border" role="status">
  <span class="visually-hidden">Loading...</span>
</div>
```

## Toasts

Toasts are lightweight notifications.

```html
<div class="toast" role="alert" aria-live="assertive" aria-atomic="true">
  <div class="toast-header">
    <strong class="me-auto">Bootstrap</strong>
    <small>11 mins ago</small>
    <button
      type="button"
      class="btn-close"
      data-bs-dismiss="toast"
      aria-label="Close"
    ></button>
  </div>
  <div class="toast-body">Hello, world! This is a toast message.</div>
</div>
```

## Tooltips

Tooltips provide additional information on hover.

```html
<button
  type="button"
  class="btn btn-secondary"
  data-bs-toggle="tooltip"
  data-bs-placement="top"
  title="Tooltip on top"
>
  Tooltip on top
</button>
```
