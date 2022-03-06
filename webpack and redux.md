# 00 - Remember

```
npx create-react-app name
```

## a. best tools to use in React

- [ ] React Router
- [ ] ramda
- [ ] lodash
- [ ] glamorous(Styling)
- [ ] Styled components
- [ ] css-modules
- [ ] Gatsby(Static websites like react website)
- [ ] Next.js(server side)
- [ ] Material-UI
- [ ] React-semantic-ui
- [ ] reselect(redux)
- [ ] reduxSaga

# 01 - ErrorBoundry In React

```react
constructor(props){
    super(props);
    this.state={
        hasEroor:false
    }
}
componenetDidCatch(error,info){
    this.setState({hasError:true});
}
```

![](C:\Users\hp\Desktop\Notes\Images\Critical render path.JPG">
  <br/>
</p>

# 02 - State Management & Redux

## 01- sample example of react app components:

![](C:\Users\hp\Desktop\Notes\Images\stateManagement.JPG">
  <br/>
</p>

## 02-Redux Solution

![](C:\Users\hp\Desktop\Notes\Images\redux solution.JPG">
  <br/>
</p>

## 03-redux ===

![](C:\Users\hp\Desktop\Notes\Images\redux equal to.JPG">
  <br/>
</p>

## action.js

```react
export const name=(props)=>({
    type:'',
    payload:type
})
```

