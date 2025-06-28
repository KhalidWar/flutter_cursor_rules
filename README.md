# Flutter Cursor Rules

A comprehensive set of coding guidelines and best practices for Flutter development, designed to work with Cursor AI IDE.

## What are Cursor Rules?

Cursor Rules are custom instructions that help the AI assistant in Cursor IDE understand your coding preferences and project conventions. By defining these rules in a `.cursorrules` file, you ensure that AI-generated code follows your team's standards and best practices.

## Purpose

This repository contains a carefully crafted set of rules specifically for Flutter/Dart development that promotes:

- **Clean Code**: Consistent naming conventions and clear code structure
- **Performance**: Best practices for efficient Flutter apps
- **Maintainability**: SOLID principles and proper design patterns
- **Type Safety**: Strong typing throughout the codebase
- **Testing**: Comprehensive testing guidelines

## How to Use

1. **Clone this repository** or copy the `.cursorrules` file
2. **Place the `.cursorrules` file** in your Flutter project's root directory
3. **Open your project in Cursor IDE** - the AI assistant will automatically use these rules

## What's Included

### Dart General Guidelines

- **Basic Principles**: Type declarations, English documentation, single exports per file
- **Nomenclature**: PascalCase for classes, camelCase for methods, underscores_case for files
- **Functions**: Short, single-purpose functions with descriptive names
- **Data**: Immutability preferences and composite types over primitives
- **Classes**: SOLID principles and composition over inheritance
- **Exception Handling**: Strategic error management
- **Testing**: Arrange-Act-Assert pattern with clear naming conventions

### Flutter-Specific Guidelines

- **State Management**: Riverpod patterns and best practices
- **Widget Architecture**: Flat widget trees for better performance
- **Theme Usage**: Proper theme color usage for light/dark mode support
- **Widget Creation**: Standalone widget classes over helper methods
- **Layout**: Modern Flutter layout techniques (spacing property)
- **Performance**: Const constructors and efficient rebuilds

## Key Benefits

### 1. Consistent Code Generation

The AI will generate code that matches your team's style guide automatically.

### 2. Better Performance

Built-in performance best practices ensure generated code is efficient from the start.

### 3. Maintainable Architecture

Promotes patterns like Repository and Controller that scale well.

### 4. Type Safety

Strong typing reduces runtime errors and improves code reliability.

### 5. Testing Focus

Encourages testable code structure and comprehensive test coverage.

## Examples

### Widget Creation (Preferred)

```dart
// ✅ Good - Standalone widget class
class _ProfileHeader extends StatelessWidget {
  const _ProfileHeader({required this.user});

  final User user;

  @override
  Widget build(BuildContext context) {
    return Container(...);
  }
}
```

### Widget Creation (Avoid)

```dart
// ❌ Bad - Helper method
Widget _buildProfileHeader(User user) {
  return Container(...);
}
```

### Theme Colors

```dart
// ✅ Good - Using theme colors
Text(
  'Hello',
  style: TextStyle(
    color: Theme.of(context).colorScheme.onSurface,
  ),
)

// ❌ Bad - Hardcoded colors
Text(
  'Hello',
  style: TextStyle(color: Colors.black),
)
```

### State Management with Riverpod

```dart
// ✅ Good - Controller pattern
class UserController extends StateNotifier<UserState> {
  UserController() : super(UserState.initial());

  void updateName(String name) {
    state = state.copyWith(name: name);
  }
}
```

## Customization

Feel free to fork this repository and modify the rules to match your team's specific needs. The `.cursorrules` file is designed to be easily customizable.

## Contributing

If you have suggestions for improving these Flutter cursor rules, please:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request with your improvements

## License

This project is open source and available under the MIT License.

## Resources

- [Flutter Documentation](https://docs.flutter.dev/)
- [Effective Dart](https://dart.dev/guides/language/effective-dart)
- [Cursor IDE](https://cursor.sh/)
- [Riverpod Documentation](https://riverpod.dev/)

---

**Note**: These rules are opinionated and based on industry best practices. Adjust them according to your team's preferences and project requirements.
