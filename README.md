# Birthday Wishing App

Built as a gift for an astronomy enthusiast, this Flutter app changes with the calendar. Once a year it opens a birthday greeting and photo carousel. Throughout the rest of the year it shows NASA's Astronomy Picture of the Day alongside a personal task list.

## Inside the app

- `lib/main.dart` chooses the opening screen from the device's date.
- `lib/pages/home.dart` fetches the daily astronomy item and saves tasks and their completion state on the device using shared preferences.
- `app.py` reads NASA's near-Earth asteroid feed and formats each object's close-approach time and miss distance. The Flutter events screen in `lib/pages/comet.dart` displays those records.

## Running a personal copy

Use a Flutter SDK with Dart 3.1.3 or later in the 3.x series. The app imports `shared_preferences`, which needs to be added to `pubspec.yaml`. Use your own greeting assets and NASA API configuration, and set the events URL in `lib/pages/comet.dart` to your own service.

Install Flask and Requests in a Python virtual environment and start the service with `python app.py`. From the Flutter project root, run `flutter pub get` and `flutter run` with an Android or iOS target. For a device, use a service address reachable from that device.
