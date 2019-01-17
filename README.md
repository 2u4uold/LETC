# Objects
## Simple objects
* Div container (SKL_Box_H/SKL_Box_V)
* Text block (SKL_Note)
* SVG icon (SKL_SVG)
* SVG icon with text (SKL_SVG_Label)
* Input (SKL_Entry) - there is one more possible

## Complex objects
* Scrollable list (_t.list.stream)
* Menu

### Text block (SKL_Box_H/SKL_Box_V)
SKL_Box_H - has flex-direction: row style, which makes all children to be in one horizontal line 

SKL_Box_V - has flex-direction: column style, which makes all children to be in one vertical line 

#### Attributes:
|Order  |Type       |       |
|---|---|---|
|1        |context    | (manager, view) |
|2        |options   |    |
|N/A      |kids    |inner content of container|
|N/A      |sys_pn       |region name to find container. can be feeded with new content|
|N/A      |kidsOpt    |Options which will be applied to all kids (mostly all common attributes can be used|

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

Also can be written wihtout SKL.

#### Example

    a =
        kind: _t.box
        flow: _a.horizontal
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
     
Where **_t.box** defines div container, and **flow** defines flex-direction


### Text block (SKL_Note)
If you want to create simple text block you need to use **SKL_Note**.

#### Attributes:
|Order  |Type       |Place to define      |Default|
|---|---|---|---|
|1      |service    |First level attribute|null   |
|2      |text       |First level attribute|"base" |
|3      |options    |First level attribute|null   |

#### Example
    SKL_Note(null, "Block header, {
        className: "header"
        service: "open-list"
    })

#### Common Attributes
|Name         |Type       |
|---          |---        |
|className    |           |
|type         |           |
|name         |           |
|service      |           |
|signal       |           |
|handler      |           |

#### Common Attributes 2
|Name         |Type       |
|---          |---        |
|radio        |           |
|state        |           |
|radiotoggle  |           |