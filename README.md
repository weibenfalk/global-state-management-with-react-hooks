# global-state-management-with-react-hooks
A try to use React Hooks for global state management

This is a modified version of Tanner Linsley's hook global state management.
Find his article here: https://blog.usejournal.com/react-hooks-the-rebirth-of-state-management-and-beyond-7d84f6026d87

I've  modified it to be able to use "split" states in with different properties in the state object.

Usage:  

In your app import the Provider component first:  

`import { Provider } from 'store'`

wrap your app as high up in the tree as possible with the component and the initial state object:  

`const initialState = {
  statePart1: {
    value1: "value1",
    value2: "value2" 
  },
  statePart2:  {
    value1: "value1",
    value2: "value2"
  }
}`

 `<Provider initialValue={initialState}>
      <BrowserRouter>
        <Switch>
          <Route path="/" exact component={HomeContainer} />
          <Route path="/:category" exact component={CategoryContainer} />
          <Route path="/:category/:id" exact component={SinglePageContainer} />
        </Switch>
      </BrowserRouter>
  </Provider>`
  
 Use it in your components like this: 

`const [state, setState] = useStore('statePart2')`


