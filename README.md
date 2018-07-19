# CS8 Backwoods Notes

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
### Landing
### Nav
### Trip
### TripList
