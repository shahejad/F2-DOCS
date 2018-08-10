# Canvas

### `Canvas`

```javascript
new Canvas(config);
```

Canvas Renderer constructor.

-  `config` : Object, the configuration needed to create a canvas object, it includes the following attributes:

| Attribute | Type | Description |
| :--- | :--- | :--- |
| `el` | String/HtmlElement | Container selector or DOM element |
| `context` | CanvasRenderingContext2D | The context of the canvas. |
| `width` | Number | Optional, width of the canvas. If it is omitted, the actual width of the canvas DOM is used by default. |
| `height` | Number | Optional, height of the canvas. If it is omitted, the actual height of the canvas DOM is used by default. |
| `pixelRatio` | Number | F2 automatically handles pixel ratio adjustments in order to render crisp drawings on all devices. Unless otherwise specified, the pixel ratio will be defaulted to the actual device pixel ratio: `window.devicePixelRatio`. You can override the device pixel ratio for special situations, or, if you don't want the pixel ratio to be taken into account, you can set it to 1. |

Example:

```javascript
const canvas = new Canvas({
  id: 'canvas',
  width: 500,
  height: 500,
  pixelRatio: 1
});
```



#### Methods

----------- 2018-08-09 ----------------------

* **getWidth\(\)**

```text
/**
 * Get width of the canvas
 * @return {Number} Corresponding width
 */
getWidth()
```

**getHeight\(\)**

```text
/**
 * Get height of the canvas's corresponding dom object
 * @return {Number} Corresponding height
 */
getHeight()
```

**changeSize\(width, height\)**

```text
/**
 * Change the size of the canvas
 * @param  {Number} width  
 * @param  {Number} height 
 */
changeSize(width, height)
```

**getPointByClient\(clientX, clientY\)**

```text
/**
 * Convert the coordinate on client window to coordinate on canvas
 * @param  {Number} clientX Coordinate of x-axis on client window
 * @param  {Number} clientY Coordinate of y-axis on client window
 * @return {Object} canvas Coordinate on canvas
 */
getPointByClient(clientX, clientY)
```

**addShape\(type, config\)**

```text
/**
 * Create a shape and add it to canvas
 * @param {String} type Type of shape to create and add
 * @param {Object} config  Configuration of the shape
 * @return {Shape} The created shape instance
 */
addShape(type, config = {})
```

The `config` parameter passed in is the configuration of the shape, includes:

```text
{
  className: String, // class name specified by users
  zIndex: Number, // hierarchical index of the shape
  visible: Boolean, // wether the shape is visible
  attrs: Object // graphic attributes of the shape, different shapes have different attributes, see Shape for more details.
}
```

**addGroup\(config\)**

```text
/**
 * Create and add a group
 * @param {Object||null} cfg Configuration for group
 * @return {Group} The created group instance
 */
addGroup(config)
```

The `config` parameter passed in is the configuration for Group, includes:

```text
{
  className: String, // user specified class name
  zIndex: Number, // hierarchical index of the group
  visible: Boolean // wether the group is visible
}
```

**add\(items\)**

```text
/**
 * Add items to canvas
 * @param {Array||Group||Shape} Items can be a shape instance, a group instance, a shape array or a group array
 * @return {Canvas}  The current canvas object
 */
add(items)
```

**contain\(item\)**

```text
/**
 * Wether current canvas contains the item
 * @param  {Shape||Group} Item can be a shape instance or group instance
 * @return {Boolean} True means canvas contains the item, otherwise it's false.
 */
contain(item)
```

**sort\(\)**

```text
/**
 * Sort the elements in the container by their zIndexes, in descending order
 * @return {Canvas||Group} The container itself
 */
sort()
```

**get\(name\)**

Get the attribute from canvas by attribute name

**set\(name, value\)**

Set the attribute value for the corresponding attribute name.

**clear\(\)**

```text
/**
  * Clear all the elements
  * @return {Canvas|Group} The container itself
  */
clear()
```

**draw\(\)**

Draw the canvas.

**destroy\(\)**

Destroy the canvas object.
