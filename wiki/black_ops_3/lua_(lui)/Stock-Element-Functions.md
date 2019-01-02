1.  Stock element functions with description
Below is a list of the important element functions that you may find useful. All functions are available for `ANY` control that extends from `UIElement`

1.  UIElement
The root element of all controls. Basically everything should extend this.

  *Usage:**

HudElem:addElement(Elem) -- All these functions use the self syntax ':'

  *Functions:**
| Function | Arguments | Description | Return values
| ----- | ----- | ----- | -----
| addElement | (UIElement: Element) | Adds an element as a child | None
| addElementBefore | (UIElement: Element, UIElement: Before) | Adds an element as a child, before the other element | None
| addElementAfter | (UIElement: Element, UIElement: After) | Adds an element as a child, after the other element | None
| canAddElement | (UIElement: Element) | Checks whether or not we can add this element | True, if we can, False if not
| unsubscribeFromAllModels | None | Unsubscribes from all model events attached to this element | None
| setModel | (Object: Model) | Sets the model for this element | None
| subscribeToGlobalModel | (Object: Instance, String: Scope, String: Item, Function: Callback(Object: Model)) | Subscribes to a global model item with the given scope | None
| subscribeToModel | (Object: Model, Function: Callback((Object: Model)) | Subscribes to the given model | None
| linkToElementModel | (UIElement: Element, String: Item, Boolean: RequiresSubscription, Function: Callback(Object: Model)) | Subscribes to the model attached to the given element | None
| isClosed | None | Checks whether or not the element was closed | True if closed, false if not
| close | None | Closes the element | None
| closeAndRefocus | (UIElement: Element) | Closes the element and moves focus to the other | None
| getSoundSet | None | Gets the current soundset for this element | The soundset name, if any
| findSoundAlias | (String: Name) | Attempts to find the given alias in the current soundset | The sound alias, if any
| playSound | (String: Name) | Plays a sound on the element with the given alias name | None
| playActionSFX | None | Plays the action sound (Same as playSound("action")) | None
| toggleMouse | None | Toggles the mouse input on or off | None
| setHandleMouse | (Boolean: Enabled) | Sets whether or not this element has mouse events | None
| toggleHandleMouse | None | Toggle whether or not this element has mouse events | None
| setHandleMouseMove | None | (Boolean: Enabled) Sets whether or not this element has mouse move event | None
| toggleHandleMouseMove | None | Toggle whether or not this element has mouse move event | None
| setHandleMouseButton | None | (Boolean: Enabled) Sets whether or not this element has mouse click event | None
| toggleHandleMouseButton | None | Toggle whether or not this element has mouse click event | None
| clearMouseFocus | None | Remove focus to this control from the mouse | None
| IsMouseInsideElement | (UIElement: Element) | Checks whether or not the mouse is over the element | True if over, False if not
| setLeftRight | (Boolean: isLeft, Boolean: isRight, Number: Left, Number: Right) | [[See Margins|http://phabricator.aviacreations.com/w/black_ops_3/lua_%28lui%29/layout_and_margins/]] | None
| setTopBottom | (Boolean: isTop, Boolean: isBottom, Number: Top, Number: Bottom) | [[See Margins|http://phabricator.aviacreations.com/w/black_ops_3/lua_%28lui%29/layout_and_margins/]] | None
| setParent | (UIElement: Element) | Sets this elements parent to the element | None
| setActive | (Boolean: BubbleToChildren) | Sets this element state to active | None
| setInactive | (Boolean: BubbleToChildren) | Sets this element state to inactive | None
| processEvent | (Table: EventObject) | Sends an event to this element | None
| processEventToParent | (Table: EventObject) | Sends an event to this element that bubbles up to the parent | None
| getRoot | None | Gets the root parent of this element | The parent element, if any
| dispatchEventToRoot | (Table: EventObject) | Sends an event to this elements root most parent | None
| dispatchEventToParentWithSelf | (Table: EventObject) | Sends an event to this elements parent, with a reference to this element | None
| dispatchEventToParentWithElement | (Table: EventObject, UIElement: Element) | Sends an event to this elements parent, with a reference to the element | None
| dispatchEventToChildren | (Table: EventObject) | Sends an event to this elements children | None
| registerEventHandler | (String: EventName, Function: Handler) | Subscribe to an event with the given name | None
| hide | None | Hides the element from view | None
| show | None | Shows the element | None
| rotateRandomly | None | Rotates the element on the X and Y axis randomly | None
| spinRandomly | None | Spins the element on the Z axis randomly | None
| flicker | None | Makes the element flicker using alpha | None
| playBitchinFX | (Unknown1, Unknown2, Unknown3) | We were as surprised as you are... | None
| playBitchinFXReverse | (Unknown1, Unknown2, Unknown3) | Opposite of playBitchinFX ... | None
| setClass | (String: Name) | Sets the class name of the element | None
| showDebugTimer | None | Shows the debug timer clip | None

  *Examples:**

1.  TODO: This will be linked to from an Examples column with source code examples below.