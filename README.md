# Developer Profile Zendesk App

Zendesk App built using Vue. Retrieves user data from 'developer-profile-api' app and displays links to user's Github and LinkedIn accounts.

![Developer Profile Zendesk App Screenshot](https://raw.githubusercontent.com/alexmckinnon/developer-profile-zendesk/master/screenshot.png)

## Development

Build Vue app and run `zat server` to run application locally.
1. Run `npm run serve` to build dist app and run zat server.
2. Open Zendesk and add `?zat=true` to URL (See Zendesk App Tools for more info)

## Package and Install App

Create a .zip file to upload application to Zendesk. The application will need a Developer Profile API endpoint URL to retrieve user data from (see developer-profile-api repo).

1. Run `npm run package` to build dist app and run zat package.
2. Follow Zendesk instructions on uploading private app
3. Add endpoint URL for the Developer Profile API
