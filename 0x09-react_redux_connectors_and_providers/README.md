# 0x09. React Redux Connectors and Providers

<p align="center">
    <img src="./project-meme.jpg"
        alt=""
        width="300"
        style="padding: 10px"
    >
</p>

## Tasks

- **0. Write mapStateToProps**

  Within the `App/App.js` file:

  - Create a function named mapStateToProps. This should connect the uiReducer you created and the property isLoggedIn that your component is already using
  - Import connect from Redux, and connect the mapStateToProps to the component

- **1. Create a small store**

  - Create a store using createStore from Redux that would contain the uiReducer state
  - Implement a provider passing the store that you created to the main App

- **2. Test MapStateToProps**

  - Create a new suite to test the function
  - Create a test that verify that the function returns the right object when passing the

  ```
    let state = fromJS({
    isUserLoggedIn: true
    });
  ```

  Should return `{ isLoggedIn: true }`

- **3. Update mapStateToProps**

  - Update the mapStateToProps function to also pass to the component the value for displayDrawer. It should be connected to the Reducer attribute isNotificationDrawerVisible
  - Update the render function of the component to use the value displayDrawer coming from the props instead of the state

- **4. Connect your actions creators**

  - Connect to the component the actions creators displayNotificationDrawer and hideNotificationDrawer
  - You should use the simplified version for the mapDispatchToProps. No need to import bindActionCreators
  - Modify the render function of the component to use the functions passed within the props instead of the action within the Class component

- **5. Refactor your code**

  - You can delete the old function handleDisplayDrawer
  - You can delete the old function handleHideDrawer
  - Remove any state property related to the display of the drawer
  - Remove any binding in the constructor
  - You are now passing to your components props. You need to define propTypes and defaultProps

- **6. Update your tests**

  - You don’t need to test the functions handleDisplayDrawer and handleHideDrawer since everything is already tested using the Redux mechanism
  - You need to update the test you previously created to support the new attribute

- **7. Async actions & Thunk middleware**

  Let’s implement the LoginRequest / logout actions creators accross the entire application. LoginRequest is calling an API and is Async. Therefore, Redux will not support it. We will need to use a middleware

  Install redux-thunk within your project. And in the index.js file, apply the middleware to your store

- **8. Connect LoginRequest to the App**

  - Connect the action creator loginRequest and map it to the login prop
  - Modify the component to use the new login function from the props instead of the one within the class
  - Refactor the component to remove any login or logout function and bind

- **9. Connect user state to the Footer**

  - Create a mapStateToProps function
  - Map the user props to the user within the Redux state
  - Connect the Footer component to the function you created
  - Modify the render function and remove any use of the Context. Instead use the user prop

- **10. Connect Logout action creator to the Header**

  - Create a mapStateToProps function
  - Map the user props to the user within the Redux state
  - Connect the Header component to the function you created
  - Connect the Header component to the logout action creator
  - Modify the render function and remove any use of the Context. Instead use the user prop. When the user clicks on the link, it should now dispatch the logout action creator

- **11. Modify the uiReducer**

  - When the action LOGIN is passed, set the user within the state to the one passed within the action
  - When the LOGOUT action is passed, make sure to set the user to nul

- **12. Modify the test suites**

  - In the App.test.js, Footer.test.js, and Header.test.js to import the Stateless components instead of the connected component
  - Remove any use of the mount function, and convert everything to use the shallow function
  - You should remove any use of setState within the tests and pass directly the props to the stateless components
  - Remove any test linked to the login, logout function within App, and Header
  - Add a test in uiReducer to support the new action you just created

- **13. Understand how to use the Redux Chrome extension**

  - Modify the index.js to support the extension
  - Use the application and note the different actions being registered when you are logging in / logging out
  - Note that a version of the state is saved along the different actions and you can jump at a different moment of the user journey

- **14. Combine store: Root reducer**

  Create a new file reducers/rootReducer.js, in this file, export a rootReducer:

  - the root should contain every reducer
  - courses maps to courseReducer
  - notifications maps to notificationReducer
  - ui maps to uiReducer

- **15. Combine store: modify the application**

  Any component connected to the state will probably need to be updated since you added a nested level

- **16. Combine store: write the tests**

  - In the App.test.js, modify mapStateToProps to correctly work with the new format of the reducer
  - Create a rootReducer.test.js file to test the root reducer’s initial state for the following structure:

- **17. Connect notifications: New Action Creator**

  Add the following three action creators to notificationActionCreators.js

  - setLoadingState whose parameter is a boolean. It will send the SET_LOADING_STATE action and the boolean.
  - setNotifications whose parameter is an array. It will send the FETCH_NOTIFICATIONS_SUCCESS action with the data.
  - fetchNotifications (which does not have a parameter). Calling it will dispatch setLoadingState with the boolean set to true
    - It fetches /notifications.json
    - Once the fetch is realized, it will dispatch setNotifications with the data
    - At the end of the query it sets the loading state to false again

- **18. Connect notifications: Improve reducer**

  - Make sure to add a loading attribute to the initial state.
  - Modify the notifications object to have the right initial state when merging the data coming from the API
  - Create a SET_LOADING_STATE case and update the state accordingly
  - Modify the FETCH_NOTIFICATIONS_SUCCESS case to perform a mergeDeep with the data

- **19. Connect notifications to the reducer**

  - Map the prop listNotifications to the messages within the notifications state
  - Map the action fetchNotifications to the component
  - In componentDidMount, call fetchNotifications

- **20. Connect notifications: clean up**

  With this new behavior, let’s clean up old functions and test data

  - Delete NotificationItemShape.js
  - Remove the notification list and delete markNotificationAsRead within App.js

- **21. Connect notifications: update the test suites**

  Modify the test suites to pass the tests:

  - Update notificationReducer.test.js to support the new attributes and default state
  - Clean up App.test.js for the function you just removed
  - Modify Notifications.js and Notifications.test.js to make sure that every tests pass correctly

  Add new tests:

  - Add a test in Notifications.test.js to verify that the function fetchNotifications is called when the component is mounted
  - Add a test for setLoadingState, setNotifications, and fetchNotifications to verify that they each create the right actions
  - Add a test for SET_LOADING_STATE to verify that it updates the reducer correctly

- **22. Selectors**

  To improve performance in your connector, you should always use selectors when you can. Let’s modify the Notifications connector to reuse the selector we built in the previous project:

  - Update Notifications.js to use getUnreadNotifications
  - Map the markAsAread action creator to the component, and use it for markNotificationAsRead

- **23. Connect courses: create a course selector**

  In selectors/courseSelector.js, create a selector that will:

  - Get all the course entities from within the reducer
  - Return a List using valueSeq from Immutable

  Write a new file courseSelector.test.js, that will verify that the selector is working correctly

- **24. Connect courses: create a fetch courses function**

  In actions/courseActionCreators.js:

  - Create a new function named fetchCourses, that will query the API in courses.json (provided in the project description, put it in your dist folder)
  - When the API returns the data, dispatch the action setCourses

  In courseActionCreators.test.js, create a test to verify that the fetch is working correctly

- **25. Connect the courses component**

  In CourseList.js, connect the component to:

  - The three action creators: fetchCourses, selectCourse, and unSelectCourse
  - Connect the data to the list of courses using getListCourses selector
  - When the component mount, call the action fetchCourses

  Create a new function onChangeRow:

  - It will take two arguments: id (string), checked (boolean)
  - When checked is true, call the action selectCourse with the id
  - When checked is false, call the action unSelectCourse with the id

  Modify CourseListRow:

  - Pass a new prop, isChecked, to the component that will pass the isSelected attribute coming from the state of the reducer
  - Pass the onChangeRow function to the component
  - Modify the component to not use its local state anymore

  In the file CourseList.test.js, create two new tests:

  - Verify that the action is dispatched when the component is mounted
  - Verify that the two actions are correctly dispatched when the onChangeRow function is called

- **26. Memoized selectors: Redux Reselect**

  Our current selectors are useful but they are not really performant. Imagine a very long list of notifications with multiple filters on the type and on the read status. This would require a lot of resources to compute. Memoized selectors are very powerful in this sense.

  Install Redux Reselect and create a new selector named getUnreadNotificationsByType in notificationSelector.js:

  - This selector should combine the state of the filter, and the list of notifications
  - When the filter is set to default, it should return all the unread notifications
  - When the filter is set to urgent, it should return all the unread and urgent notifications
  - Delete getUnreadNotifications

- **27. Memoized selectors: update the UI**

  In the Notifications component:

  - Update the component to use the new selector you just created
  - Map the component to the Action setNotificationFilter
  - Add two buttons under the text Here is the list of notifications. The first one contains ‼️. On click, it set the filters of notifications to URGENT. The second one contains 💠. On click, it sets the filter of notifications to DEFAULT

- **28. Memoized selectors: update the test suite**

  In Notifications.test.js, add two new tests:

  - Clicking on the first button should call setNotificationFilter with URGENT
  - Clicking on the second button should call setNotificationFilter with DEFAULT

  In notificationSelector.test.js:

  - Update the previous tests to work correctly
  - Create a new test to verify that the selector returns unread urgent notifications when the filter is set

- **29. Container/Component**

  Our components can become very verbose when we start adding connectors and actions. It is also becoming harder to tests what is supposed to be our React component, and the interations of the application. To simplify our architecture, we can use the concept of containers and components:

  - Create a new file NotificationsContainer.js. This component will take care of connecting to the state, and fetching the notifications on mount
  - The component should render the Notifications components and pass the required props to it
  - Modify the file Notifications.js. It should now become a functional component
  - Create a new test file for NotificationsContainer.js. It should make sure the fetching is happening on mount
  - Modify Notifications.test.js file to only support the new behavior of the file
