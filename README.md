# compass-flexbox

A collection of [Compass](http://compass-style.org/) mixins providing [the best
possible browser support](http://css-tricks.com/using-flexbox/) for the
[CSS Flexible Box Layout Module](http://dev.w3.org/csswg/css-flexbox/).

[Test page](http://stevenbenisek.github.io/compass-flexbox/)

## Installation

You can download from this repository or install with [Bower](http://bower.io/).

```bash
bower install compass-flexbox
```

Once installed import `_flexbox.scss` in your sass file after importing
[Compass](http://compass-style.org/).

```sass
@import
    'compass',
    'path-to/flexbox';
```

## Naming

All mixins are named according to the current spec and prefixed with an 'x-',
e.g. `@include x-display('flex')`. The former is to get used to the offical
property and value names. The latter clearly indicates these mixins are custom 
and also avoids any current or future naming collisions with other frameworks.

## Mixins

##### Flex container
- [display](#display)
- [flex-direction](#flex-direction)
- [flex-wrap](#flex-wrap)
- [flex-flow](#flex-flow)
- [justify-content](#justify-content)
- [align-items](#align-items)
- [align-content](#align-content)

##### Flex item
- [order](#order)
- [flex-grow](#flex-grow)
- [flex-shrink](#flex-shrink)
- [flex-basis](#flex-basis)
- [flex](#flex)
- [align-self](#align-self)

---
<a></a>
### Display

[Test page](http://stevenbenisek.github.io/compass-flexbox/#display)

#### Flex

##### Example:

```scss
.flex-container {
    @include x-display('flex');
}
```
returns:
```css
.flex-container {
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
}
```

##### Browser support:

- IE 10+
- <sup>**[1](#notes-display)**</sup> Firefox 3.6+
- Chrome 4+
- Safari 3.1+
- Opera 12.1+
- iOS Safari 3.2+
- ~~Opera Mini~~
- Android 2.1+
- Opera Mobile 12.1+
- Blackberry 7+
- IE Mobile 10

<a name="notes-display"></a>
###### Notes:

1. Firefox 19- treats flex-containers as inline-block elements. Explicitly
set `width: 100%;` to counter this.

#### Flex-inline

##### Example:

```scss
.flex-container {
    @include x-display('inline-flex');
}
```
returns:
```css
.flex-container {
    display: -ms-inline-flexbox;
    display: -webkit-inline-flex;
    display: inline-flex;
}
```

##### Browser support:

- IE 10+
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- IE Mobile 10

---
<a></a>
### Flex-direction

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-direction)

##### Example:

```scss
.flex-container {
    @include x-flex-direction('row');
}
```
returns:
```css
.flex-container {
        -webkit-box-orient: horizontal;
           -moz-box-orient: horizontal;
     -webkit-box-direction: normal;
        -moz-box-direction: normal;
    -webkit-flex-direction: row;
        -ms-flex-direction: row;
            flex-direction: row;
}
```

##### Browser support:

- IE 10+
- Firefox 3.6+
- Chrome 4+
- Safari 3.1+
- Opera 12.1+
- iOS Safari 3.2+
- ~~Opera Mini~~
- Android 2.1+
- Opera Mobile 12.1+
- Blackberry 7+
- IE Mobile 10

---
<a></a>
### Flex-wrap

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-wrap)

##### Example:

```scss
.flex-container {
    @include x-flex-wrap('wrap');
}
```
returns:
```css
.flex-container {
    -webkit-flex-wrap: wrap;
        -ms-flex-wrap: wrap;
            flex-wrap: wrap;
}
```

##### Browser support:

- <sup>**[1](#notes-flex-wrap)**</sup> IE 10+
- ~~Firefox~~
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- <sup>**[1](#notes-flex-wrap)**</sup> IE Mobile 10

<a name="notes-flex-wrap"></a>
###### Notes:

1. In IE10+ `flex-wrap` doesn't work combined with `flex-direction: column`

---
<a></a>
### Flex-flow

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-flow)

##### Example:

```scss
.flex-container {
    @include x-flex-flow('column nowrap');
}
```
returns:
```css
.flex-container {
    -webkit-flex-flow: column nowrap;
        -ms-flex-flow: column nowrap;
            flex-flow: column nowrap;
}
```

##### Browser support:

- <sup>**[1](#notes-flex-flow)**</sup> IE 10+
- ~~Firefox~~
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- <sup>**[1](#notes-flex-flow)**</sup> IE Mobile 10

<a name="notes-flex-flow"></a>
###### Notes:

1. In IE10+ `flex-flow` doesn't work when the direction is `column`

---
<a></a>
### Justify-content

[Test page](http://stevenbenisek.github.io/compass-flexbox/#justify-content)

##### Example:

```scss
.flex-container {
    @include x-justify-content('flex-start');
}
```
returns:
```css
.flex-container {
           -webkit-box-pack: start;
              -moz-box-pack: start;
              -ms-flex-pack: start;
    -webkit-justify-content: flex-start;
            justify-content: flex-start;
}
```

##### Browser support:

- IE 10+
- <sup>**[1](#notes-justify-content)**</sup> Firefox 3.6+
- <sup>**[1](#notes-justify-content)**</sup> Chrome 4+
- <sup>**[1](#notes-justify-content)**</sup> Safari 3.1+
- Opera 12.1+
- <sup>**[1](#notes-justify-content)**</sup> iOS Safari 3.2+
- ~~Opera Mini~~
- <sup>**[1](#notes-justify-content)**</sup> Android 2.1+
- Opera Mobile 12.1+
- <sup>**[1](#notes-justify-content)**</sup> Blackberry 7+
- IE Mobile 10

<a name="notes-justify-content"></a>
###### Notes:

1. No support for the `space-around` value. Firefox 22+, Chrome 21+, Safari 6.1+, 
iOS Safari 7 and Blackberry 10 have full support.

---
<a></a>
### Align-items

[Test page](http://stevenbenisek.github.io/compass-flexbox/#align-items)

##### Example:

```scss
.flex-container {
    @include x-align-items('flex-start');
}
```
returns:
```css
.flex-container {
      -webkit-box-align: start;
         -moz-box-align: start;
         -ms-flex-align: start;
    -webkit-align-items: flex-start;
            align-items: flex-start;
}
```

##### Browser support:

- IE 10+
- Firefox 3.6+
- Chrome 4+
- Safari 3.1+
- Opera 12.1+
- iOS Safari 3.2+
- ~~Opera Mini~~
- Android 2.1+
- Opera Mobile 12.1+
- Blackberry 7+
- IE Mobile 10

---
<a></a>
### Align content

[Test page](http://stevenbenisek.github.io/compass-flexbox/#align-content)

##### Example:

```scss
.flex-container {
    @include x-align-content('flex-start');
}
```
returns:
```css
.flex-container {
       -ms-flex-lign-pack: start;
    -webkit-align-content: flex-start;
            align-content: flex-start;
}
```

##### Browser support:

- IE 10+
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- IE Mobile 10

---
<a></a>
### Order

[Test page](http://stevenbenisek.github.io/compass-flexbox/#order)

##### Example:

```scss
.flex-item {
    @include x-order(2);
}
```
returns:
```css
.flex-item {
    -webkit-box-ordinal-group: 2;
       -moz-box-ordinal-group: 2;
               -ms-flex-order: 2;
                -webkit-order: 2;
                        order: 2;
}
```

##### Browser support:

- IE 10+
- Firefox 3.6+
- Chrome 4+
- Safari 3.1+
- Opera 12.1+
- iOS Safari 3.2+
- ~~Opera Mini~~
- Android 2.1+
- Opera Mobile 12.1+
- Blackberry 7+
- IE Mobile 10

---
<a></a>
### Flex-grow

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-grow)

##### Example:

```scss
.flex-item {
    @include x-flex-grow(2);
}
```
returns:
```css
.flex-item {
     -webkit-box-flex: 2;
        -moz-box-flex: 2;
    -webkit-flex-grow: 2;
        -ms-flex-grow: 2;
            flex-grow: 2;
}
```
##### Browser support:

- IE 10+
- Firefox 3.6+
- Chrome 4+
- Safari 3.1+
- Opera 12.1+
- iOS Safari 3.2+
- ~~Opera Mini~~
- Android 2.1+
- Opera Mobile 12.1+
- Blackberry 7+
- IE Mobile 10

---
<a></a>
### Flex-shrink

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-shrink)

##### Example:

```scss
.flex-item {
    @include x-flex-shrink(2);
}
```
returns:
```css
.flex-item {
      -ms-flex-negative: 2;
    -webkit-flex-shrink: 2;
            flex-shrink: 2;
}
```

##### Browser support:

- <sup>**[1](#notes-flex-shrink)**</sup> IE 10+
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- <sup>**[1](#notes-flex-shrink)**</sup> IE Mobile 10

<a name="notes-flex-shrink"></a>
###### Notes:

1. In order for `flex-shrink` to work in IE10+ you have to explicitly declare a
`flex-shrink` value for all other flex items (usually you would set the value to
1).

---
<a></a>
### Flex-basis

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex-basis)

##### Example:

```scss
.flex-item {
    @include x-flex-basis(200px);
}
```
returns:
```css
.flex-item {
    -ms-flex-preferred-size: 200px;
         -webkit-flex-basis: 200px;
                 flex-basis: 200px;
}
```

##### Browser support:

- IE 10+
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- IE Mobile 10

---
<a></a>
### Flex

[Test page](http://stevenbenisek.github.io/compass-flexbox/#flex)

##### Example:

```scss
.flex-item {
    @include x-flex(1 1 200px);
}
```
returns:
```css
.flex-item {
    -webkit-flex: 1 1 200px;
        -ms-flex: 1 1 200px;
            flex: 1 1 200px;
}
```

##### Browser support:

- IE 10+
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- IE Mobile 10

---
<a></a>
### Align-self

[Test page](http://stevenbenisek.github.io/compass-flexbox/#align-self)

##### Example:

```scss
.flex-item {
    @include x-align-self('flex-start');
}
```
returns:
```css
.flex-item {
    -ms-flex-item-align: 'start';
     -webkit-align-self: 'flex-start';
             align-self: 'flex-start';
}
```

##### Browser support:

- ~~IE~~
- Firefox 22+
- Chrome 21+
- Safari 6.1+
- Opera 12.1+
- iOS Safari 7
- ~~Opera Mini~~
- ~~Android~~
- Opera Mobile 12.1+
- Blackberry 10
- ~~IE Mobile~~

## Further browsing

- [Using Flexbox: Mixing Old and New for the Best Browser Support](http://css-tricks.com/using-flexbox/)
- [Caniuse](http://caniuse.com/flexbox)
- [Flexyboxes](http://the-echoplex.net/flexyboxes/)
- [Solved by Flexbox](http://philipwalton.github.io/solved-by-flexbox/)
- [Learn you a flexbox](http://www.the-haystack.com/2012/01/04/learn-you-a-flexbox/)

