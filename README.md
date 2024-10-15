# responsive-design-initiative

Our Responsive Design initiative is all about being able to display and operate ioBroker responsively on all end devices. 
In order to provide a guide and overview of the many existing adapters, here is a guide for jsonConfig and Materialize Adapter.

The most important points that need to be taken into account in the adapters for display on mobile devices are listed here.

---

## jsonConfig Adapter

For jsonConfig, all resolutions should be taken into account in the respective inputs.

The following resolutions are provided:
* xl - width in 1/12 of screen on extra large screens (1536px < width)
* lg - width in 1/12 of screen on large screens (1200px <= width < 1536px)
* md - width in 1/12 of screen on middle screens (900px <= width < 1200px)
* sm - width in 1/12 of screen on small screen (600px <= width < 900px)
* xs - width in 1/12 of screen on tiny screens (width < 600px)

### We recommend the following values for the standard layout

````
"xs": 12,
"sm": 12,
"md": 6,
"lg": 4,
"xl": 4
````

### The following entry should be made below ` "type": "tabs"` in order to display a clearly legible table bar:

````
"tabsStyle": {
  width: "calc(100% - 100px)"
},
````

---

## Materialize Adapter

For adapters in the Materialize design, important classes for the correct resolution should also be used for mobile devices.

### List of classes for different display sizes:

* lx - width in 1/12 of screen on large screens (1200px <= width < 1536px)
* mx - width in 1/12 of screen on middle screens (900px <= width < 1200px)
* sx - width in 1/12 of screen on small screen (600px <= width < 900px)

The recommended values for a `<div>` are as follows:

````
<div class=‘col s12 m6 l4’>
````

The classes s,m and l must be configured in each `<div>`.

### Custom css for the mobile resolution

If you use your own CSS styles in your adapters, you should define the necessary values for the mobile resolution in the area. The area must be listed as follows in the CSS:

````
/* Style for small Screens */
@media screen and (max-width: 768px) {

}
````

````
/* Style for very small Screens */
@media screen and (max-width: 600px) {

}
````