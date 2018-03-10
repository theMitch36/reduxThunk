Redux Thunk Notes:

1. Redux-thunk is used for async action creators 
2. Redux is arround to help us maintain our application state, it allows us to change the apps state in a very well defined pattern. the pattern is:
    a. we call an action creator, which produces an action
    b. the action flows into our middleware(connect?), then into our reducers
    c. and our reducers producer our new application state, which then flows into react
    d. then we wait for the user to trigger another action that repeats the process all over again

3. * the steps listed above work perfectly for syncrounous actions, but thats not too helpful with async
4. Vanilla redux is not good at handling async, out of the box, thats where redux-thunk comes into play
5. Redux-Thunk gives us direct controll over the dispatch method.
    a. the dispatch method is apart of the redux store that contains the apps state.    
    b. when we call an action creator that returns an action, the action is passed into the dispatch method
    c. the dispatch method is a big funnel, that takes in an action and makes sure it gets passed to all the reducers => new application state
6. when our action creator sends an action to our reducers, it is expecting it to come across as a returned Object, but Redux Thunk allows us to return a function to our reducers for the async calls
    a. the functions takes 2 arguments, dispatch method &     