# CS8 Backwoods Frontend Notes

In this file I'll be talking about some of the scaffolding decisions behind the frontend of the CS8 file structure and route layout. If you're not sure where you should be contributing, this is a good reference sheet to help you get acquainted with the structure of the frontend of this application.

## File structure

To begin with, this is the basic file structure of the frontend. I'll then go through each folder and talk about what content belongs in them, as well as any unique files that require explanation.

```
src
└── components
    ├── Account
    ├── Billing
    ├── Debug
    ├── Landing
    ├── Nav
    ├── Trip
    └── TripList
```

### Account

This is for all NON BILLING account-related changes. Like if a user needs to change their password, email, or delete their account. Maybe in the future adding a contact support link here too could be nice too.

### Billing

This is for BILLING information. If a user has not purchased their subscription, being linked here will give them the opportunity to do that. Otherwise, if a user is already subscribed and authenticated, this page should show data about their subscription (like time related) and offer a prompt to cancel their subscription or change their credit card info and etc.

### Debug

This is for internal debug components. It won't be included in the production build of the client. It just makes the frontend developer's lives a little bit easier by giving the opportunity to navigate to any view without having to click through the entire application and find the page they're looking for.

### Landing

This is for the landing page. Users will see the landing page if they navigate to the website and are NOT logged in. They will have the opportunity to sign up, log in, and buy the product from here.

### Nav

This is for all navigation components. That includes the vertical navbar, the breadcrumbs, and the sign out button. They will be visible on every page except the landing page.

### Trip

This is for INDIVIDUAL trips. NOT the list of all trips. From this view, you'll be able to check in to your waypoints as well as view the map for the user trip. Additionally in this folder is the `TripCreate` file, which is the component that should appear when a user clicks the `New Trip` button.

### TripList

This is the LIST of trips. If there are no trips, the `TripsEmpty` component should appear and prompt a user to create their first trip. If the signed in user does have trips, `Trips` will appear and have a small preview. The user can then click on the trip to view or modify it, or archive it.

---

## Understanding some of the more complicated files

### Nav

So inside the nav there's four different files:

```
Nav
├── Nav.jsx
├── NavBar.jsx
├── NavBreadcrumbs.jsx
└── SignOut.jsx
```

The `Nav.jsx` component is to act as an index for the output of the Nav component. The `Navbar.jsx`, `NavBreadcrumbs.jsx`, and `SignOut.jsx` components all feed into it, and then `Nav.jsx` is used through the rest of the application where the user will see a nav (which is almost every page of the application)

### Trip List

The trip list might be a little bit confusing. It should be a list of trips (probably by mapping through an array in the database or something similar) that the user has created. If, however, that array of lists is empty, it should display `TripListEmpty.jsx` and prompt a user to create a trip, rather than showing a list of trips.

### Trip vs TripCreate

`Trip.jsx` is a single Trip. It will show the map as well as a list of waypoints. It relates to Trip (Open) in the balsamiq previews. `TripCreate.jsx` is the component that appears when the user clicks the prompt to make a new trip.
