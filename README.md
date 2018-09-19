# Flexi Widget

Reusable, mobile responsive Vue component

## Installation

```js
npm i --save-dev flexi-widget
```

### Browser

Include the script file, then install the component with `Vue.use(FlexiWidget);` e.g.:

```html
<script type="text/javascript" src="node_modules/vuejs/dist/vue.min.js"></script>
<script type="text/javascript" src="node_modules/flexi-widget/dist/flexi-widget.min.js"></script>
<script type="text/javascript">
  Vue.use(FlexiWidget);
</script>
```

### Module

```js
import FlexiWidget from 'flexi-widget';
```

## Usage

Once installed, it can be used as simply as:

```html
<flexi-widget :color="'blue'"
              :header="'Flexi Widget'"
              :result="202030"
              :progressBar="50">
</flexi-widget>
```

```css
.container{
    display: flex;
    //optionial 
    #use flex-direction: 'column' or 'row'
}
```

## API

### Props

| Name        | Type           | Description                                                             |
| :-----      | :-------       | :---------------------------------------------------------------------- |
| color       | String         | Changes the theme color of the flexi widget.                             |
| header      | Sting          | Set a header.                                 |
| result      | String Number  | Set a main value in the widget                           |
| progressBar | Number         | Set a value for progress bar                           |