1.  Stock LUI elements (controls) you can use
Below is a list of all of the builtin controls that are available. They are all apart of the `LUI` namespace.

1.  Element.new(Object: Parent, Object: Instance)
This is the default ctor of all elements, when setting the parent, it tells the layout what to base the margins from.

1.  UIElement
This is the root of all UI elements. It is also very useful for a grid-like container and can house child controls with ease. If you are creating a new element, this is the control to override.

1.  UIText
This element displays text on the hud. You can set the font color with `setRGB`. The font size is directly connected to the height of the control and will scale that way. The width however does not effect the drawing and will overflow if need be. You can also set the font with `setTTF("fonts/font-name.ttf")` using a font included in your zone via: `ttf,fonts/font-name.ttf`.

1.  UIImage
This element can display an image (2D) or a background color with `setRGB`. When using `setImage` you must use `RegisterImage` to register the image name in LUI. For instance, if you want to use the `$white` image, you would do `setImage(RegisterImage("$white"))` on the control. The UIImage control stretches the image to fit the width and height of the element.

1.  UIStreamedImage
This element functions like a `UIImage` however, it supports waiting for a streamed image to load in. On load, it displays a loading indicator `Treyarch Spinner` while waiting for the image. This element also exposes an event for the image being ready: `streamed_image_ready(Sender, EventArgs)`

1.  UIVerticalList
This element allows stacking elements vertically. Controls added with `addElement` get added to the bottom of the list. In addition, you can use `addSpacer` to add a divider between the elements.

1.  UIHorizontalList
This element allows stacking elements horizontally. Controls added with `addElement` get added to the right of the list. In addition, you can use `addSpacer` to add a divider between the elements.

1.  UIList
This element functions similar to a `UIVerticalList` however it also exposes a scrollbar for overflowing content (`UIVerticalList` does not scroll).

1.  UIButton
This element houses the base for a clickable control. It exposes events for hover, leave, click, mousedown and mouseup. It can be customized with other controls for a different look and feel.