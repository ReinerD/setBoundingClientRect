setBoundingClientRect
=====================

A tiny helper Javascript which allows to set the axis aligned bounding box of arbitrary svg elements, with respect to the transformations applied on it

The usage is pretty simple, since it creates a prototype function for all SVGElements, you just need to type:
<code>element.setBoundingCLientRect( rect )</code>
where rect must be an object that privides:
<code>x, y, width, height</code>
properties.
The function returns an object of the type <code>SVGMatrix</code> which when applied to the element by: i.e. appending it to its transform list will transform the element into its new bounding box. If the transform matrix of the element is not invertable, what happens if the element is f.e. scaled down to zero in one or both directions, than the function returns <code>null</code>.

The function accepts a second, optional parameter that is called: <code>apply</code> and is a boolean value. If set and set to true the calculated matrix will be applied to the element by either initiliazing its transformlist or appending an new item to it. Take in account that this will increase the number of transform items in the list by one each time the method is called on the same element and if this happens to often performance will suffer. But its up to you to manage the transformlist and if you decide to apply the matrix you also may decide to consolidate the list.

Please report bugs! Enjoy!
