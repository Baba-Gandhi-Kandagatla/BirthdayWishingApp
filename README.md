# Birthday Wishing App

## Introduction

A Flutter birthday gift for an astronomy enthusiast. The opening screen changes with the calendar.

## Tech stack

Flutter and Dart provide the mobile UI. Shared preferences store tasks on the device. A Python Flask service uses Requests to retrieve NASA near-Earth object data.

## Features

- Annual birthday greeting with a photo carousel.
- Astronomy Picture of the Day and a personal task list on ordinary days.
- Asteroid close-approach times and miss distances from NASA’s feed.

## The process

- `lib/main.dart` chooses the opening screen from the device's date.
- `lib/pages/home.dart` fetches the daily astronomy item and saves tasks and their completion state on the device using shared preferences.
- `app.py` reads NASA's near-Earth asteroid feed and formats each object's close-approach time and miss distance. The Flutter events screen in `lib/pages/comet.dart` displays those records.

## How it can be improved

Moving the greeting date, image list and service address into a single configuration file would let someone adapt the app for another recipient without editing the screens.

## How to run

Use a Flutter SDK with Dart 3.1.3 or later in the 3.x series. The app imports `shared_preferences`, which needs to be added to `pubspec.yaml`. Use your own greeting assets and NASA API configuration, and set the events URL in `lib/pages/comet.dart` to your own service.

Install Flask and Requests in a Python virtual environment and start the service with `python app.py`. From the Flutter project root, run `flutter pub get` and `flutter run` with an Android or iOS target. For a device, use a service address reachable from that device.

## Screenshots

<img src="docs/images/birthday-screen.png" alt="Birthday greeting with confetti and an illustrated bear." width="245">
