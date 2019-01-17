# LETC Objects
## Simple objects
* Div container
* Text block
* SVG icon
* SVG icon with text
* Input

## Complex objects
* Scrollable list
* Menu
* Form

### Div container

Object, which can contain other objects

#### Unique attributes:
|Name |Possible values|Explanation|
|---|---|---|
|kind |"box"|Defines container object|
|flow |"vertical"/"horizontal"|Vertical or horizontal direction of children elements|
|kids |Array|Array of children elements|
|kidsOpt |Object|Options which will be applied to all children elements (Common attributes)|
|sys_pn |String |Name of region, can be feeded with children elements. Allows to have access to container element|
|__other common attributes__| | |

#### Example
    a =
        kind: "box"
        flow: "horizontal"
        className: "block"
        kidsOpt  :
            radio: "radio-group"
        kids: [
            SKL_Note(null, "Block header, {
                className: "header"
            })
            SKL_Note(null, "Block subheader, {
                className: "header"
            })
        ]

Alternative variant of defining container is **SKL_Box_H/SKL_Box_V**. Has two attributes.
* SKL_Box_H - has __flex-direction: row__ style, which makes all children to be in one horizontal line 
* SKL_Box_V - has __flex-direction: column__ style, which makes all children to be in one vertical line 


#### Attributes:
|Attribute order  |Type |Possible values |Explanation |
|---|---|---|---|
|1        |context    | (manager, view) | |
|2        |options   |Object | Defines additional attributes|
|Inside 2 |kids    |Array |Array of children elements|
|Inside 2 |sys_pn       |region name to find container. can be feeded with new content|
|Inside 2 |kidsOpt    |Options which will be applied to all kids (mostly all __common attributes__ can be used|

Example above can be written whit way

#### Example
    SKL_Box_H(manager, {
        className: "block"
        kidsOpt  :
            radio: "radio-group"
        kids: [
            SKL_Note(null, "Block header, {
                className: "header"
            })
            SKL_Note(null, "Block subheader, {
                className: "header"
            })
        ]
    })

### Text block

Allows to create any text objects

#### Unique attributes:
|Name |Possible values|Explanation|
|---|---|---|
|kind |"note"|Defines text object|
|content |String|Text|
|__other common attributes__| | |
|__other low level objects attributes| | |

#### Example
    a =
        kind: "note"
        content: "Block header"
        className: "header"

Alternative variant of defining text is **SKL_Note**.

#### Attributes:
|Attribute order  |Type |Possible values |Explanation |
|---|---|---|---|
|1      |service    |String|Service name (see __common attributes__)|
|2      |text       |String|Any text|
|3      |options    |Object |Defines additional attributes|

#### Example
    SKL_Note(null, "Block header, {
        className: "header"
        service: "open-list"
    })

__service__ can be written both as first attribute or as part of Options attribute

### SVG icon

Allows to create svg icon

#### Unique attributes:
|Name |Possible values|Explanation|
|---|---|---|
|kind |"image_svg"|Defines svg icon object|
|chartId |String|Icon name|
|__other common attributes__| | |
|__other low level objects attributes| | |

#### Example
    a =
        kind: "image_svg"
        chartId: "arrow-left"
        service: "turn-left"

Alternative variant of defining text is **SKL_SVG**.

#### Attributes:
|Attribute order  |Type |Possible values |Explanation |
|---|---|---|---|
|1      |text    |String|Icon name|
|2      |options    |Object |Defines additional attributes|
|3      |size    |{<p>width: 40,</p><p>height: 40,</p><p>padding: 10</p> }|Object which contains width, height and padding of icon.|

#### Example
    SKL_SVG("arrow-left, {
        className: "header"
        service: "open-list"
    }, {
        width: 35
        height: 20
        padding: 12
    })

To be continued

#### Common Attributes
|Name         |Type       |
|---          |---        |
|className    |           |
|type         |           |
|name         |           |
|service      |           |
|signal       |           |
|handler      |           |
|styleOpt||
|anim||
|flow||

#### Low level objects attributes
|Name         |Type       |
|---          |---        |
|radio        |           |
|state        |           |
|radiotoggle  |           |
