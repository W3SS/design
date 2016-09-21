---
title: Navigation
template: child-2col-coded
active_page: 'selected'
snippet_title: Selected Page
notes: 'A nav-item with full green background indicates the current page that the user is on.'
example: '<nav class="navigation">
  <a class="current">
    <i class="icon-users"></i>
    <span class="label">Users</span>
  </a>
</nav>'
---

* [HTML](0)
* [SCSS](1)

```html
<nav class="navigation">
  <a class="current">
    <i class="icon-users"></i>
    <span class="label">Users</span>
  </a>
</nav>
```
```sass
.navigation {
  margin-bottom: 0;

  > a {
      @include transition(background, color);

      color: inherit;
      display: block;
      font-size: 14px;
      line-height: 26px;
      padding: 8px 12px;
      position: relative;
      text-decoration: none;

      &:focus {
          transition-duration: 0s;
      }

      &:hover, &:focus {
          color: $duo-green;
      }

      &.current {
          background: $duo-green;
          color: white;

          .new {
            border-color: white;
            color: white;
          }

          &:hover {
              background: $duo-green-dark;
          }
      }

      .flexbox & {
          display: flex;
          align-items: baseline;

          .label {
              flex: 1;
          }
      }
  }

  [class^="icon"] {
      display: inline-block;
      font-size: 16px;
      margin-right: 12px;
      opacity: 0.8;
      text-align: center;
      width: 18px;

      .flexbox & {
          align-self: center;
      }
  }

  .count, .new {
      font-size: small;
      opacity: 0.5;
      position: absolute;
      top: 10px;
      right: 16px;

      .flexbox & {
          position: absolute;
      }
  }

  .new {
      border: 2px solid $duo-green;
      border-radius: $border-radius;
      color: $duo-green;
      font-size: 11px;
      height: 20px;
      line-height: 11px;
      padding: 2px;

      & + .count {
          display: none;
      }

      &.expired + .count {
          display: block;
      }
  }
}
```