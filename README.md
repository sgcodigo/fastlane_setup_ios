# Codigo - Fastlane setup

This repo consists of the files required to setup Fastlane in a typical iOS app.

All the files, except `.env.sample` are meant to be copied and pasted into the project directory of any iOS project.

## Features

* Updates Fastlane gem version every time any lane is executed.
* Auto increment App version number meant for tracking app version used for testing during UAT.
* Auto increment App **build** and **version** number for appstore (production) build
* Pings to codigogroup's Slack account when any lane has completed. Channel and Project Manager to ping to can be configured in `.env` file.
* Uploads to Codigo's AWS account where the ipa are stored for easy download via a standard url.

## Usage

Replace `.env.sample` with `.env` and change all the values (keep the keys) according to your project requirements.

Run the commmand in terminal based on the lane to build. Eg for UAT,

```
fastlane uat
```

For first time setup, one may need to run this command to setup Fastlane match:

```
fastlane match init
```

### Folders and files

Copy the `fastlane` folder into your root project directory.

Copy `Gemfile` file into your root project directory.

Copy `Settings.bundle` folder into your project's workspace directory.

## Extra steps

### `app_rating_config_path`
`app_rating_config_path` will look at `fastlane/metadata/itunes_rating_config.json` file. The params are negative by default, which ffits of the configurations of most of our apps.

### 'app_icon'
Require `appicon.png` to be place in `fastlane/metadata/` folder, named exactly as shown. Change accordingly if need be.

## Known errors

* `fastlane produce` will throw error: `User doesn't have enough permission for the following action: user_details_data`
* First time gym will throw error
