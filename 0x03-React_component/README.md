# 0x03. React component

<p align="center">
    <img src="./project-meme.jpeg"
        alt=""
        width="300"
        style="padding: 10px"
    >
</p>

## Tasks

- **0. Commence with class components**

  Convert the App function into a React Class:

  - Modify the function within App.js to convert the App function into a React class
  - Make sure that the tests are still passing
  - [App.js](./task_0/dashboard/src/App/App.js)

- **1. Lifecycles**

  Add lifecycle to a component.<br>
  In the App Class:

  - Add a props named logOut with the props type being function
  - The default value for this property, should be an empty function
  - Add an event listener when the component is mounted to listen to when the user is pressing down the keyboard keys
  - When the user is pressing down the control and the h keys simultaneously, display the alert Logging you out and call the function logOut

  Add the tests<br>
  In the test file for the App Class:

  - Create a test to verify that when the keys control and h are pressed the logOut function, passed as a prop, is called and the alert function is called with the string Logging you out
  - [App.js](./task_1/dashboard/src/App/App.js), [App.test.js](./task_0/dashboard/src/App/App.test.js)

- **2. Handling Events**

  Create a new handing event<br>
  In the Notifications component:

  - Convert the function into a React Class
  - Make sure that the tests are still passing
  - Create a new markAsRead function within the Notifications class. It accepts one argument: id(number)
  - When the function is called, it logs to the console the message “Notification $id has been marked as read
  - Pass the function markAsRead to the NotificationItem component as a property

  In the NotificationItem Class:

  - Modify the li element to call the new function markAsRead on click. It should send the id of the notification
  - Define the new property type and the default property for the new properties

  Add the tests<br>
  In the Notifications test file:

  - Create a test, that will mockup the console.log function
  - Check that when calling the function markAsRead on an instance of the component, the spy is being called with the right message

  In the NotificationItem test file:

  - Create a test, that will pass a spy as the markAsRead property
  - Check that when simulating a click on the component, the spy is called with the right ID argument
  - [NotificationItem.js](./task_2/dashboard/src/Notifications/NotificationItem.js), [NotificationItem.test.js](./task_2/dashboard/src/Notifications/NotificationItem.test.js), [Notifications.js](./task_2/dashboard/src/Notifications/Notifications.js), [Notifications.test.js](./task_2/dashboard/src/Notifications/Notifications.test.js)

- **3. Reusable comments & specialization**

  Create a new component named BodySection. The component does not know its children. It should output the following:

  - A div with the class bodySection
  - Within the div, a h2 element containing a title passed as a prop
  - Under the h2 the children of BodySection
  - [BodySection.js](./ask_3/dashboard/src/BodySection/BodySection.js)

- **4. Specialization**

  in `task_3/dashboard/src/BodySection/BodySectionWithMarginBottom.js`, create a new component named BodySectionWithMarginBottom. The component does not know its children. It should output the following:

  - A div with the class bodySectionWithMargin
  - Within the div, a BodySection element with the same props passed to bodySectionWithMargin

  in `task_3/dashboard/src/BodySection/BodySectionWithMarginBottom.css`

  - Set the style for the class bodySectionWithMargin with a margin bottom of 40px
  - Import the styling into the BodySectionWithMarginBottom component
  - [BodySectionWithMarginBottom.js](./task_3/dashboard/src/BodySection/BodySectionWithMarginBottom.js), [BodySection.css](./task_3/dashboard/src/BodySection/BodySection.css)

- **5. Use the new components**

  - Wrap the CourseList component with the newly created BodySectionWithMarginBottom component. The title should be Course list
  - Wrap the Login component with the newly created BodySectionWithMarginBottom component. The title should be Log in to continue
  - Using the BodySection component, add a new block with the title News from the School. The component should contain a paragraph with some random text
  - [App.js](./task_3/dashboard/src/App/App.js)

- **6. Test the new components**

  - Add one test checking that shallowing the component should render correctly the children and one h2 element
  - Add one test checking that shallowing the component should render correctly a BodySection component and that the props are passed correctly to the child component
  - [BodySection.test.js](./task_3/dashboard/src/BodySection/BodySection.test.js), [BodySectionWithMarginBottom.test.js](task_3/dashboard/src/BodySection/BodySectionWithMarginBottom.test.js)

- **7. Create WithLogging HOC**

  We would like to add a way to log to the console every time a component has been mounted and every time it is about to unmount.<br>
  To not repeat the same code everywhere, create a HOC component in `task_4/dashboard/src/HOC/WithLogging.js`:

  - The component should log to the console Component NAME_OF_THE_WRAPPED_COMPONENT is mounted on componentDidMount()
  - The component should log to the console Component NAME_OF_THE_WRAPPED_COMPONENT is going to unmount on componentWillUnmount()
  - Modify the displayName of the HOC to always display WithLogging(NAME_OF_THE_WRAPPED_COMPONENT) in the React Chrome Extension or for debugging
  - NAME_OF_THE_WRAPPED_COMPONENT should be the name of the wrapped component or class. If the wrapped element has no name it should default to Component
  - [WithLogging.js](./task_4/dashboard/src/HOC/WithLogging.js)

- **8. Write a test for the HOC**

  write some tests for the HOC component:

  - The first test should make sure console.log was called on mount and on unmount with Component when the wrapped element is pure html
  - The second test should make sure console.log was called on mount and on unmount with the name of the component when the wrapped element is the Login component. Component Login is mounted and Component Login is going to unmount should be sent to the console
  - [WithLogging.test.js](./task_4/dashboard/src/HOC/WithLogging.test.js)

- **9. Declare a pure component**

  - Modify the component to make it “pure”. Which means that it will only update when its props and state are different
  - [NotificationItem.js](./task_5/dashboard/src/Notifications/NotificationItem.js)

- **10. Make your own pure component**

  - Modify the file so it only updates itself when the new property listNotifications has a longer list of elements than the previously
  - You must implement the function shouldComponentUpdate to add this performance optimization
  - [Notifications.js](./task_5/dashboard/src/Notifications/Notifications.js)

- **11. Add a test**

  add two checks:

  - The first check should verify that when updating the props of the component with the same list, the component doesn’t rerender
  - The second check should verify that when updating the props of the component with a longer list, the component does rerender
  - [Notifications.test.js](./task_5/dashboard/src/Notifications/Notifications.test.js)
