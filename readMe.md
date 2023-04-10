## 3 core concepts of redux

**store**: Holds the state of your application
**action**: Describes what happened. It describes the changes in the state of tyhe application.
**Reducer**: Ties the store and action together. It carries out the state transition depending of the action.

## Three principles
*The state of ypur application is stored in an object tree within a single store. Maintain our application state in a single object which would be managed by the redux store.

*The only way to change the state is to emit an action, an object describing what happened.
*To specify how the state tree is transformed by actions, write pure reducers.


## Actions
The ONLY way your appliation can interact with th store.
Carry some information from your app to the redux store.
plain javascript objects.

```bash
function BuyCake(){
    return
    {
        type: 'buy cake',
        payload:{
            INFO: 'DEY PLAY'
        }
    }
}

```

## Reducer
```bash

    # store
    const initialState = {
        numberOfCake :10
        numberOfIceCream: 15
    }

    function reducer (state = initialState, action){
        switch(action.tye){
            case: 'buy cake:
            return { ...state, numberOfCakee- 1};
            break;
           default: return state
        }
    }


```

## store
 responsibilities:
 * Holds application state
 * Allows access via **getState()**
 * Allows state to be updated via **disatch(action)**
 * Register listnera via **subscribe(listner)**
 handles unregistering of listners via the function returned by subscribe(listner)

 creating a store

 ```bash
 import redux from 'redux'

 const createStore =  redux.createstore 
 const store =  createStore(reducer) ----- responsibility 1

 console.log('initial State' , store.getstate()) ----- responsibility 2

 store.subscribe(()=>{  ------ responsibility 4
    console.log('updated store' : store.getState())
 })


 store.dispatch(BuyCake())----- responsibility 3
 store.dispatch(BuyCake())----- responsibility 3
 store.dispatch(BuyCake())----- responsibility 3

const unsubscribe =  store.subscribe(()=>{  ------ responsibility 4
    console.log('updated store' : store.getState())
 })

 unsubscribe() ------ responsibility 5

 ```


 ## Multiple Reducers
 ```bash

    const initialCakestate= {
        numberOfCakes : 10
    }
    const initialIcecreamState = {
        numberOfIcecream = 20
    }


    function handleIceCream({
        return {
            type: buy_iceCream
        }
    })

    function BuyCake(){
    return
    {
        type: 'buy cake',
        payload:{
            INFO: 'DEY PLAY'
        }
    }
}

    function icecreamReducer(state= initialIcecreamState  , action ){
        switch(action.type){
            case 'buy_iceCream':
            return {...state, numberOfIcecream - 1 }
            default: return state
        }
    }

        function reducer (state = initialCakestate , action){
        switch(action.tye){
            case: 'buy cake:
            return { ...state, numberOfCakee- 1};
            break;
            default: return state
        }
    }



 ```