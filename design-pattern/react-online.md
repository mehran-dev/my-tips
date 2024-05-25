### react design pattern

- HOC (Prop Proxy | Inheritance-Inversion )
  {pp => adds to prop | ii adds sth to render method it is useless now }
- presentational container
- hook form
- render props
- compound components
- props combination
- controlled input
- props collection
- props getter/setter
-

#### visit site below

[design-pattern-site](https://www.patterns.dev/react/)

[hoc dev dev.to site ](https://dev.to/sayanide/understanding-react-higher-order-component-hoc-4i06)

- [inversion of control](https://kentcdodds.com/blog/the-state-reducer-pattern-with-react-hooks)

- prop Getters Pattern

[When to use Control Props or State Reducers
](https://kentcdodds.com/blog/control-props-vs-state-reducers)

### the state initializer pattern

The state initializer pattern allows you to expose an API to users to be able to reset your component to its original state without having to completely unmount and remount the component.

### Kent C Dods Course

- Context module function
- Compound component
  each is useless and share implicit state

```javascript
  <CustomSelect
  options={[
    {value:1, display:"hello"},
    {value:2, display:"bye"},
  ]}
  >


//real word example : REACH-UI / @reach-ui/tooltip / 2reach-ui/accordion

const [on,setOn]= useState(true)

<Toggle>
<ToggleOn on  children/>
<ToggleOff/>

</Toggle>

```

### props collections and getters

prop collection => tgglerProps
prop getter => getTgglerProps

```javascript
<Switch on={on} {...togglerProps} />
<Switch on={on} {...getTogglerProps} />


const callAll (...fns){
  return (...args)=>{
    fns.forEach(fn=>{
      fn?.(..args)
    })
  }
}


onClick=()=>{callAll(onClick , toggle )}
```

### state reducer pattern (great implementation of inversion of control )

```javascript
const { on, getTogglerProps, getResetProps } = useToggle({
  reducer: userCustomReducer,
});
```

### control props

- downshift
- @reach/listbox

```javascript

<input
 value={val}
 onChange=(e)=>setVal(e.target.value)
/>

```

### visit this repo for this course

[github](https://github.com/ohansemmanuel/advanced-react-patterns-ultrasimplified)

[mo.js for animation ](https://mojs.github.io/tutorials/getting-started.html#setup-mo-js-in-your-project)

### compound component benefits

```javascript
 1- customization
 2- props overload

// preventing of this :
 <MedumClamp
 clapProps={}
 countTotalProps={}
 clapIconProps={}

 />
// by doing this :
<MediumClamp>
  <ClampIcon props={}/>
  <ClampTotal props={}/>
  <ClampCount props={}/>
</MediumClamp>
// Or
<MediumClamp>
  <MediumClamp.Icon props={}/>
  <MediumClamp.Total props={}/>
  <MediumClamp.Count props={}/>
</MediumClamp>


// how to have count  outside of clamp ?

const onClap =(count)=>{
setMyCount(count)
}

<MediumClamp onClamp={onClamp}>
  <MediumClamp.Icon props={}/>
  <MediumClamp.Total props={}/>
  <MediumClamp.Count props={}/>
</MediumClamp>
<div>{you clamped {myCount} time }</div>



```

### props collection

```javascript
togglerProps={

};

counterProps={
  count:count ,
  "aria-valuemax":MAX
  "aria-valuemin":MIN
  "aria-valuenow":NOW
  "aria-pressed":true
}

<Clap counterProps={counterProps} >
<Clap.Total {...counterProps} >
</Clap>


```

### props getter

```javascript


 <Component   {...propsCollection}

 //  this overrides the propsCollection
    "aria-label":"click-here"

 />
// ===============================================================

getProps =(props)=>{
  return {
    "aria-pressed":props.clicked
    "aria-label":"click-here",
    onClick =-> what if user wants its own onClick
    ...props,
  }
}


 <Component   {...getProps()}



 />

```

### state initializer pattern

```javascript
//reset the state to its initial state

// preventing reset if state is not changed !!!
```

```javascript
// how usePrevious works

//write a button to update state if previous user input is not equal !
usePrevious (value)=>{
  const ref = useRef()
    useEffect(() => {
    // this doesn't run for the first time !!!
      ref.current =value
    }, [])
    return ref.current
}


```

### state reduce pattern

```javascript
 give user ability to pass a reducer and manage your internal  state  externally

// write hob game with this

<Input

value ={}
onChange={}

/>

<Input

reducer={reducer}

>
//Input =>

const [value , dispatch]= useReducer(reducer, initialSate , init )


<input value={value}  onChange={e=>dispatch(e.target.value)}>




```

inversion of control
<Input
validator={userValidator}
 />

‍‍‍‍‍```

end of one of our courses

```javascript

 container/presentational component




 const [state , setState] = useSate()
 <Container>
  <Presentation1  state={stateOrPartOfState} >
  <Presentation2  state={stateOrPartOfState} >
  <Presentation3  state={stateOrPartOfState} >
  <Presentation4  state={stateOrPartOfState} >

 </Container>




// or you can do  this :

<ResourceLoader>
  <UserInfo>
</ResourceLoader>


```

### functional programming

- controlled component
- function component
- hoc
- recursive component
- partially applied component
- component composition

```javascript
// recursive pattern
 const listMenu ={
  a:{
    b:c
  },
  x:y,
  z:{
    w:
    {
      p:
      {oops:Foo:
        {Bar:Baz}
      }
      }
  }
 }
//TODO Add recursive function to render the listMenu



// CompositionalPattern

// 1) Button ---> <Button></Button>

// 2) DangerButton ----> <Button className="red"></Button >


// Partially Applied
// creation
  hoc => partiallyApply (Comp , partialProps)=>{
  return props=>{

    <Component {...partialProps }{...props} >
  }
 }


// usage

  const DangerButton = partiallyApply(Button , {bg:red , size:"large"})

```

linkedin Shaun Wassell
