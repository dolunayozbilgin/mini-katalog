# Copilot Instructions for mini_katalog

## Project Overview
- **mini_katalog** is a cross-platform Flutter app (Dart) for product catalog browsing, with support for Android, iOS, web, macOS, Linux, and Windows.
- Main app entry: `lib/main.dart`.
- Core features: product listing, detail view, and cart management.

## Architecture & Structure
- **Screens**: UI pages in `lib/screens/` (e.g., `home_screen.dart`, `detail_screen.dart`, `cart_screen.dart`).
- **Models**: Data structures in `lib/models/` (e.g., `product.dart`, `product_data.dart`).
- **Widgets**: Reusable UI components in `lib/widgets/` (e.g., `product_card.dart`).
- **Platform code**: Native integration in `android/`, `ios/`, `macos/`, `linux/`, `windows/`.

## Data Flow & Patterns
- Product data is defined in `lib/models/product_data.dart` and modeled by `product.dart`.
- Screens access product data directly from model files (no backend/API integration by default).
- State is typically managed locally within widgets/screens (no global state management library).

## Developer Workflows
- **Run app**: `flutter run` (auto-detects platform)
- **Build APK**: `flutter build apk`
- **Web build**: `flutter build web`
- **Run tests**: `flutter test` (tests in `test/`)
- **Hot reload**: Use `r` in terminal during `flutter run`

## Conventions & Patterns
- Use Dart idioms and Flutter best practices for widget composition.
- UI logic is separated into screens and widgets; avoid business logic in UI code.
- Product data is static and local; update `lib/models/product_data.dart` to change catalog.
- No custom code generation or build_runner usage.

## Integration Points
- No external API or database by default.
- Add dependencies via `pubspec.yaml` and run `flutter pub get`.
- Platform-specific code (e.g., push notifications) should be added in respective platform folders.

## Examples
- To add a new product: update the list in `lib/models/product_data.dart`.
- To add a new screen: create a Dart file in `lib/screens/` and register it in navigation logic in `main.dart`.

## Key Files
- `lib/main.dart`: App entry, navigation setup
- `lib/models/product_data.dart`: Product catalog data
- `lib/screens/`: UI screens
- `lib/widgets/`: UI components

---
For more, see [README.md](../README.md) or Flutter docs.
