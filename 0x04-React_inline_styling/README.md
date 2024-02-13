# 0x04. React inline styling

<p align="center">
    <img src="./project-meme.jpg"
        alt=""
        width="300"
        style="padding: 10px"
    >
</p>

## Tasks

- **0. Inline styling**

  Modify the `CourseListRow` component in `task_0/dashboard/src/CourseList/CourseListRow.js`:

  - Using inline styling, change the background color of a row to #f5f5f5ab
  - Using inline styling, change the background color of a header row to #deb5b545
  - If needed, modify the test file so every test pass
  - [task_0](./task_0/)

- **1. install Aphrodite**

  Install Aphrodite using npm with:

  `npm install --save aphrodite`

  Modify the `App` component in `task_1/dashboard/src/App/App.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the body and the footer within the file
  - Delete the file App.css and the import

  Modify the `BodySectionWithMarginBottom` component in `task_1/dashboard/src/BodySection/BodySectionWithMarginBottom.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the margin within the file
  - Delete the file BodySection.css and the import

  Modify the `CourseList` component in t`ask_1/dashboard/src/CourseList/CourseList.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the list within the file
  - Remove the styling for the list within the CourseList.css file

  Modify the `Header` component in `task_1/dashboard/src/Header/Header.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the logo and the header within the file
  - Delete the file Header.css and the import

  Modify the `Login` component in `task_1/dashboard/src/Login/Login.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the margin within the file
  - Delete the file Login.css and the import

  Modify the `Notifications` component in `task_1/dashboard/src/Notifications/Notifications.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the notifications panel within the file
  - Remove the styling for the notifications panel from the Notifications.css
  - [task_1](./task_1/)

- **2. Conditionally applying style**

  Modify the `NotificationItem` component in `task_2/dashboard/src/Notifications/NotificationItem.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the urgent and default items
  - Using condition, apply the styling to the li element
  - Delete the Notifications.css file and remove any import

  Modify the `NotificationItem.test` suite in `task_2/dashboard/src/Notifications/NotificationItem.test.js`:

  - Make sure that tests are still passing

  Modify the `CourseListRow` component in `task_2/dashboard/src/CourseList/CourseListRow.js`:

  - Modify the component to use Aphrodite within the js file
  - Define the styling for the different type of rows (default rows, header rows)
  - Define the styling for the different type of th elements
  - Delete the CourseList.css file and remove any import

  Modify the `CourseListRow.test` suite in `task_2/dashboard/src/CourseList/CourseListRow.test.js`:

  - Make sure that tests are still passing
  - Test properties one by one if easier
  - [task_2](./task_2/)

- **3. Responsive design**

  Let’s make the application responsive to the screen size using media queries. We are going to only focus on large screen and screens with a width under 900px

  Modify the component `Login` in `task_3/dashboard/src/Login/Login.js`:

  - Make sure that a label and an input are on each line
  - Make sure that the button is on a new line
  - The screen should look like the image below:

  Modify the component `Notifications` in `task_3/dashboard/src/Notifications/Notifications.js`:

  - When the panel is open, it should take over the entire screen
  - There should be no padding because of the ul element
  - The font size of the text should be 20px

  Modify the component `NotificationItem` in `task_3/dashboard/src/Notifications/NotificationItem.js`:

  - The item should take the entire screen width
  - A black border should be displayed at the bottom
  - The font size of the text should be 20px
  - The padding for the item should be 10px 8px
  - [task_3](./task_3/)

- **4. Animation**

  Let’s create an animation that we can display when the user hovers on the `Notifications` menu or when there is a new notification. In `task_4/dashboard/Notifications/Notifications.js`:

  - Create one object containing the CSS frames to make the opacity change from 0.5 to 1
  - Create one object containing the CSS frames to make the element bounce. You can play with translateY and alternate from 0px to -5px and 5px

  Modify the styling for the menu item to:

  - Float on the right of the screen over every element
  - The background color should be #fff8f8
  - Show the pointer cursor when hovering the element
  - On hover, animate the element with the two new animations. The duration for the opacity change should be 1s, and the duration for the bouncing effect should be 0.5s. The animation should repeat 3 times only
  - When the list of notifications is visible, hide the menu item
  - [task_4](./task_4/)
