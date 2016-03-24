# react-animated-number
React component for animating numbers

## Usage

```js
import AnimatedNumber from 'react-animated-number';
...
...

class Demo extends Component {

    ...

    render () {
        <AnimatedNumber component="text" value={bigValue}
            style={{
                transition: '0.8s ease-out',
                fontSize: 48,
                transitionProperty:
                    'background-color, color, opacity'
            }}
            frameStyle={perc => (
                perc === 100 ? {} : {backgroundColor: '#ffeb3b'}
            )}
            frameDuration={16} duration={300}
            format={n => prettyBytes(n)}/>
    }
}
```
## API

#### value: number
**required**<br/>
Numeric value to which to tween to

----

#### component: any
**default**: `"span"`<br/>
This is similar to the react transition [API](https://facebook.github.io/react/docs/animation.html#rendering-a-different-component). By default, renders text inside a `<span>`. You can pass in any valid `ReactElement`. Use `"text"` for rendering into SVG.

----

#### format: ?(percentage: number) => string
A callback function that accepts a number and returns a formatted string

----

#### duration: ?number
**default**: `300`<br/>
Total duration of animation in milliseconds

----

#### frameDuration: ?number
**default** `16`<br/>
Duration of each animation frame in milliseconds.

----

#### frameStyle: ?(perc: number) => Object | void,
A callback function that accepts the percentage of completion of current animation and returns the style object to applied to the current frame

----

#### stepPrecision: ?number
**default** `2`<br/>
The number of decimal places to render for intermediate values.
If set to `0`, rounds of intermediate values using `Math.round`


<br/>


## Demo
A demo can be found [here](http://ameyms.com/react-animated-number/).
Source code for the demo can be found [here](https://github.com/ameyms/react-animated-number/blob/master/example/demo.jsx).

## License
react-animated-number is licensed under MIT license.