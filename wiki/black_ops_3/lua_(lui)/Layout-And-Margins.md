1.  Information regarding responsive layout and margins
This page will go over how to design your layout and also how margins work.

1.  Setting a margin on a UIElement
To set the margins on an element you would do something like:

-- (bool: IsDistanceFromLeft, bool: IsDistanceFromRight, MarginLeft, MarginRight)
Element:setLeftRight(true, true, 0, 0)
-- (bool: IsDistanceFromTop, bool: IsDistanceFromBottom, MarginTop, MarginBottom)
Element:setTopBottom(true, true, 0, 0)

This specific margin layout tells our control to fit to it's container. (0 pixels from each corner)

1.  Margins infographic
Below is a visual representation of how margins work:
{F18849,size=full,layout=center}