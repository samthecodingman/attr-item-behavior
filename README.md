# AttrItemBehavior

[![Currently in beta](https://img.shields.io/badge/status-beta-yellow.svg)](https://www.github.com/samthecodingman/attr-item-behavior) [![Not suitable for production](https://img.shields.io/badge/production--ready-no-red.svg)](https://www.github.com/samthecodingman/attr-item-behavior#to-do-list) [![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/samthecodingman/attr-item-behavior) [![Only dependency is polymer](https://img.shields.io/badge/dependencies-only--polymer-green.svg)](https://www.github.com/samthecodingman/attr-item-behavior#usage-instructions) [![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/samthecodingman/attr-item-behavior/blob/master/LICENSE)

A behavior that reflects the properties of an object to an element's attributes.

### Usage Instructions

`Polymer.AttrItemBehavior` defines the properties and functions that reflect the
properties of the object specified as the `attr-item` attribute to this element.

At this time, all public properties of the `attrItem` object will be
reflected to this element (a public property is one not prefixed with
an underscore). If the propery has no definition, it will be defined as
one that notifies and is reflected as an attribute on this element.

**Dependencies:** This element is only dependent on Polymer itself when deployed.

## Example

`attr-item` must be used with an object data binding and therefore the parent
element must also be a Polymer element. (Please post an issue or PR if you can
get it to work).

Both one-way and two-way data bindings are possible. However, the attributes
created by this behavior **WILL** notify and change value if bound on the parent
element.
```html
<attr-demo attr-item="{{someObject}}"></attr-demo>
<!-- or -->
<attr-demo attr-item="[[someObject]]"></attr-demo>
```

Custom Element Definition:
```html
<dom-module id="attr-demo">
  <template>
    <p><em>[[value]]</em> came from the attr-item object.</p>
  </template>

  <script>
    Polymer({
      is: 'attr-demo',
      behaviors: [ Polymer.AttrItemBehavior ],
    });
  </script>
</dom-module>
```

## To Do List
This is a brief list of tasks that are yet to be completed. Feel free to open an issue or contribute a pull request if you think you can help.
- Implement Tests
- Make configuration object to set defaults for newly bound keys
- Make bindings work with nested objects.

More information can be found on the [documentation pages](https://samthecodingman.github.io/attr-item-behavior/).
