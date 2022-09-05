### UI components
Developed with `@headlessui/react` and powered by `@floating-ui/react-dom-interactions`.

## CountryCode
Simple component to select country code with country flag. Developed with `react-country-flag` lib.

```js
<CountryCode
  onChange // for updating/getting selected country details
  contentPos=""
  placement='bottom-end'
  arrowCls='w-3 h-3'
  btnCls=""
/>
```

Quick start 
```js
<CountryCode
  onChange={val => console.log(val)}
/>
```

## DateHlp
Component for date handling which is powered by `react-datepicker` library.

```js
<DateHlp
  value // selected date value
  onChange // update the selected date
  className='' // wrapper classname
  dateFormat="dd/MM/yyyy"
  dayClassName={dayCNDefault} // function returns string for the day cell
  showPopperArrow={false}
  {...otherPropertiesOfReactDatepicker}
/>
```

Quick start 
```js
const [selected, setSelected]=useState(new Date())

<DateHlp
  value={selected}
  onChange={setSelected} // date => console.log(date)
/>
```


## DropDown
Mutli-level dropdown component. It is the most complicated ui component. Everything in Dropdown is button and by default list box, placed bottom. If the component in parent then onClick function is not called, its children will be shown. It exports several individual components, given bellow

```js
  import { Menu, MenuItem, MenuComponent, DropDownWrapper } from "DropDown";
```

For basic use cases, use `DropDownWrapper`.


`MenuItem - Individual items`
```js
<MenuItem 
  label // string | Component
  value="" // if label is Component then we have to provide its value
  disabled // boolean
  className=""
  active="" // currently active item name/value
  activeCls=""
  {...otherProps}
/>
```
onClick function is passed from MenuComponent.


`MenuComponent - Wrapper for the menu items box`
```js
<MenuComponent 
  label // string | component (Parent)
  children // menu items
  onClk // onClick function of menu items
  rootCls="" // parent button className
  rootActiveCls="" 
  className=""
  boxCls="" // list item box className
  animeOrigin="" // anmition origin
  boxStyle={} // if boxCls can't perform the need then style object can be passed
  placeAt="bottom" // floating ui placement
  isFixed={false} // floating ui strategy
  needArrow={false} // triangle arrow indicating parent 
  arrowCls="" // triangle arrow className
  preventClose={false} // does need to close list box onClicking the menu item
  offsetProps={} // floating ui offset property
  withHover={true} // show list box on hover
  {...otherProps}
/>
```


`Menu - Wrapper for the menu items`
```js
<Menu 
  label // string | Component
  children
/>
```


`DropDownWrapper - Predefined component using the above three components`
```js
<DropDownWrapper 
  list // array -> to represent the menu items
  onClk // onClick menu item. we will get the string or value (if item is object)
  children // string | Component (Parent)
  btnCls="" // common className for the menu items
  active="" // currently active item name/value
  activeCls=""
  {...otherProps}
/>
```

`list - prop of DropDownWrapper in detail` - list can be an array of strings or objects. If the menu item is simple a word alone, then we can use strings, If we want to show some elements with menu item or we want to show children, we can use object.
The structure of the object is given below,

```js
{
  value, // to represent the item
  label, // string | component
  list, // array. if we want to show children 
}
```

Quick start 
```js
const list = [
  "Item 1" ,
  "Item 2", 
  {
    value: "Item 3",
    label: <><img src='' /> Item 3</>
  },
  {
    value: "Item 4",
    label: <><img src='' /> Item 4</>,
    list: [
      "Item 4.1",
      "Item 4.2",
      {
        value: "Item 4.3",
        label: <><img src='' /> Item 4.3</>
      }
    ]
  }
]

<DropDownWrapper
  list={list}
  onClk={val => console.log(val)}
>
  Wrapper
</DropDownWrapper>
```

```js
<Menu label='Wrapper' onClk={val => console.log(val)}>
  <MenuItem label="Item 1" />
  <MenuItem label="Item 2" />
  <Menu label="Item 2">
    <MenuItem label="Item 2.1" />
    <MenuItem label="Item 2.2" />
  </Menu>
</MenuItem>
```


## Modal
Modal ui component. by default placed at center, we other four options configured also. If we want place the item in the right side, then we can use `placeAt=""`. If we want place the item in the left side, then we can use `placeAt="end"`. `placeAt="centerBtm"` is act as center as for the big screens and will act as placed bottom of the screen in the mobile screens.

```js
<Modal
  isOpen={true} // state of the modal
  closeModal // function for closing the modal
  children // content of the modal
  overlayCls="" // outer box 
  placeAt="center" // ("" | center | centerBtm | end) placement of the content decider
  transition={} // object (Transition props)
  wrapperCls="" 
  contentCls=""
  contentStyle={} // to overwrite styles
/>
```

Quick start 
```js
const [open, setOpen] = useState(false)

const updateOpen = () => setOpen(p => !p)

<button onClick={updateOpen}>
  Click me
</button>

<Modal
  isOpen={open}
  closeModal={updateOpen}
>
  Modal content
</Modal>
```


## RadioInput
Radio input box to select only one value from the list of options.

```js
<RadioInput
  value // selected radio iput value
  onChange // update the selected value, we will get the string or key (if item is object)
  list // array (string | object) -> to represent the radio input items
  label="" // label for the radio group
  labelCls=""
  wrapperCls="" // wrapper of the radio inputs alone not the label
  contentCls=""
  checkedCls="bg-main-900"
  activeCls='outline-main-900'
  unactiveCls='outline-gray-600'
  inputCls=""
  textCls=''
  disabled={false}
/>
```

`list - prop of RadioInput in detail` - list can be an array of strings or objects. The structure of the object is given below,

```js
{
  key, // to represent the option's value
  Comp // string | cmponent
}
```

Quick start 
```js
const list = [
  "Option 1",
  "Option 2",
  {
    key: "Option 3",
    Comp: <><img src='' /> Option 3</>
  }
]

const [selected, setSelected] = useState("")

<RadioInput
  list={list}
  value={selected}
  onChange={setSelected}
/>
```


## Select
Replacer for html select box.

```js
<Select
  value // selected value
  onChange // update the selected value, we will get the string or key (if item is object)
  list // array (string | object) -> to represent the items
  btnCls="" // button for selecting the list
  arrowCls=""
  contentCls=""
  optionCls="py-2 px-4"
  activeCls="text-white bg-main-900"
  unactiveCls="text-gray-800"
  selectedCls="font-medium"
  unselectedCls="font-normal"
  placeholder=""
  placeholderCls="text-s5 text-[#8e9cb6]"
  lable=""
  lableCls=""
  transition={} // @headlessui/react's Transtion component's transtions related props. 
  strategy='absolute' // @floating-ui/react-dom-interactions's useFloating's strategy property
  placement='bottom-end' // @floating-ui/react-dom-interactions's useFloating's placement property
/>
```

Quick start 
```js
const list = [
  "Option 1",
  "Option 2",
  {
    key: "Option 3",
    Comp: <><img src='' /> Option 3</>
  }
]

const [selected, setSelected] = useState("")

<Select
  list={list}
  value={selected}
  onChange={setSelected}
/>
```


## SelectWithInput
Same as Select with searchable functionality.

```js
<SelectWithInput
  value // selected value
  onChange // update the selected value, we will get the string or key (if item is object)
  list // array (string | object) -> to represent the items
  query='' // search string
  setQuery // updater of the search string
  NotFoundComp={null} // String|Comp (optional). To show no match found
  contentCls=""
  btnCls=""
  arrowCls="mr-2"
  optionCls="py-2 px-4"
  activeCls="text-white bg-main-900"
  unactiveCls="text-gray-800"
  selectedCls="font-medium"
  unselectedCls="font-normal"
  placeholder=""
  lable=""
  lableCls=""
  inputCls=''
  transition={}
  strategy='absolute'
  placement='bottom-end'
/>
```

Quick start 
```js
const list = [
  "Option 1",
  "Option 2",
  {
    key: "Option 3",
    Comp: <><img src='' /> Option 3</>
  }
]

const [selected, setSelected] = useState("")
const [query, setQuery] = useState("")

<SelectWithInput
  list={list}
  query={query}
  value={selected}
  setQuery={setQuery}
  onChange={setSelected}
/>
```


## Tabs
Tab ui component based on index.

```js
<Tabs
  tabsList // array of strings 
  children // can have the same number of children according to the tabsList. ordered by tabsList order. Arrange the children one by one.
  onChange // update the selected tab
  selectedIndex={0} // selected tab index
  tabClass="" 
  spanClass="" // line under the tab name
  listClass="" // tab list wrapper
  panelClass="" // wrapper for all children
  panelChildCls="" // wrapper for the individual child
  selectedTabCls="" // currently selected/active tab in the tabsList
  unselectedTabCls="" // unselected/unactive tab in the tabsList
/>
```

Quick start 
```js
const tabsList = ["Tab 1", "Tab 2", "Tab 3"]
const [selected, setSelected] = useState(0)

<Tabs
  tabsList={tabsList}
  onChange={setSelected}
  selectedIndex={selected}
>
  <div>Tab 1 Child</div>
  <div>Tab 2 Child</div>
  <div>Tab 3 Child</div>
</Tabs>
```


## Toggle
Switch component for showing on/off ui.

```js
<Toggle
  checked // true | false, state of the switch on/off
  onChange //update the toggler state
  disabled={false}
  btnCls=""
  wrapperCls=""
  checkedCls="right-1"
  uncheckedCls="left-1"
  checkedWrapCls="bg-[hsla(236,69%,58%,.6)]"
  uncheckedWrapCls="bg-[#E0E0E2]"
/>
```

Quick start 
```js
const [selected, setSelected] = useState(false)

<Toggle
  checked={selected}
  onChange={() => setSelected(p => !p)}
/>
```