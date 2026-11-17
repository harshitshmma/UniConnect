# UniConnect

UniConnect is a prototype web app that helps university students find peers who can teach them a topic or a hands-on skill. A student signs up with their university, writes a short bio, and searches for other students by what they know.

**Status:** early prototype. The login and two of the three search pages are demos. See [Current state](#current-state).

## The problem

Students often need help with a specific subject or practical skill, such as a tricky physics topic or getting started with Arduino. They usually do not know who on campus or at nearby universities can help. UniConnect puts those people in one searchable place.

## How it works

1. **Login (`index.html`):** the student enters name, email, university (LPU, Chandigarh University or Delhi University) and mobile number. A new user is saved to a Firestore `users` collection.
2. **Dashboard (`dashboard.html`):** shows the student's name and university, lets them edit a bio and profile photo URL, and lets them choose an expert type. The page background changes with the university.
3. **Professional experts (`experts.html`):** searches the bios of all users in Firestore and shows matching cards.
4. **Topic experts (`Topic.html`):** quick picks for Physics, Chemistry and Mathematics plus a free-text topic search.
5. **Practical experts (`practical.html`):** quick picks for Robotics, Arduino, Electronics and Web Projects plus a free-text skill search.

## Tech

- HTML, CSS and plain JavaScript, no build step
- Firebase Firestore for user data
- Browser `localStorage` for the signed-in user, bio and profile photo
- Google Fonts (Poppins, Montserrat)

## Current state

What works:
- Saving a new user to Firestore at login
- Editing and auto-saving a bio on the dashboard
- Searching user bios on the Professional experts page

What is a demo or not finished:
- **Login:** the OTP step is a placeholder. The app shows "OTP sent (demo only)" and does not check the code you enter.
- **Topic and Practical search:** these pages record the search term and show "No data yet". They are not connected to the database.
- **Data:** nothing here is meant for real student data. Use fake details when trying it out.

## Run it locally

1. Download or clone this repository.
2. Open `index.html` in a browser, or serve the folder with any static server.
3. The app uses the author's Firebase project. To use your own, replace the `firebaseConfig` object in `index.html`, `experts.html` and `practical.html`, and create a Firestore database.

## Planned next steps

- Replace the demo OTP with real authentication (Firebase Authentication)
- Connect Topic and Practical search to the database
- Add Firestore security rules so users can only read the profile fields meant to be public
- Add screenshots and a hosted demo link

## Author

Built by Harshit, a B.Tech Robotics and Automation student at Lovely Professional University, Punjab.
