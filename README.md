A Flutter package that allows you to access translated strings without having to pass context.

## Features

Before:
```dart
Text(AppLocalizations.of(context)!.appTitle);
```

After:
```dart
Text(S.current.appTitle);
```

Not having to pass context is especially useful when you need to access translations outside the widget build tree like a controller class, bloc etc.

### Statically typed

Unlike other packages with similar functionality you can access your translation keys in a statically typed way, as properties, and not as raw strings that you have to be copying over. The compiler will prevent you from making any mistakes that would otherwise be discovered during runtime.

### Extension not replacement

This package is an extension to the original Flutter localization toolchain and does not replace any parts of it nor it requires the use of specialized IDE extensions.

## Getting started

1. Follow the official guide ["Internationalizing Flutter apps"](https://docs.flutter.dev/development/accessibility-and-localization/internationalization).

2. In your `pubspec.yaml` add:

```yaml
dependencies:
  current_context: ^0.0.1
```

## Usage

0. Run the `flutter gen-l10n` command once to verify that the localization files are generated. Normally this step is not needed.

1. Import the generated localizations file:
```dart
import 'package:flutter_gen/gen_l10n/app_localizations.dart';
```

2. Use `S.curent.xyz` to access your translated message.

## Additional information

### Preheat

This package will auto-initialize during the first runtime use. If you want to force initialization you can call:
```dart
S.preheat()
```
You can do that in the main function of your project.

### No need to specify non nullable getters

There is no need to set `nullable-getter: false` to avoid having to deal with nullable strings.

### Use at your own risk

This package is currently experimental and the API might change. 

Since potential issues might arise only use at your own risk.

If you spot an issue please open an issue or even better make a PR that fixes it.