# Flutter Food Menu App

A simple and responsive Flutter application that displays a restaurant menu with dishes, images, and prices.  
The app supports both **mobile** and **tablet/desktop** layouts using responsive design techniques.

---

## Features

| Feature | Description |
|----------|-------------|
| 🧭 **Navigation Drawer** | Contains categories like Main Dishes, Desserts, and Drinks. |
| 🖼️ **Menu Cards** | Displays dishes with image, name, and price. |
| 💬 **SnackBar Notifications** | Shows messages when selecting categories or adding dishes to cart. |
| 🧩 **Responsive Design** | Automatically switches between grid (Wrap) and list (Column) layout based on screen width. |
| 🛒 **Floating Action Button** | “Order” button to simulate placing an order. |

---

## App Structure

```
lib/
├── main.dart        # Entry point of the app
├── MyApp            # Root widget for the application
├── HomePage         # Main screen with menu and navigation drawer
└── MenuCard         # Custom widget displaying each food item
```

---

## How It Works

### 1. **Responsive Layout**
```dart
final screenWidth = MediaQuery.of(context).size.width;
final bool isWide = screenWidth > 600;
```
- If `isWide` → uses a `Wrap` layout for multiple columns.  
- If not → uses a `Column` layout for vertical stacking.

### 2. **Drawer Navigation**
```dart
Drawer(
  child: ListView(
    children: [
      ListTile(title: Text('Main Dishes')),
      ListTile(title: Text('Desserts')),
      ListTile(title: Text('Drinks')),
    ],
  ),
)
```
Each category shows a brief `SnackBar` message when selected.

### 3. **MenuCard Widget**
Displays a dish with image, name, and price, plus an "Add" button:
```dart
MenuCard(
  title: 'Phở bò',
  price: 45000,
  imageName: 'phobo.webp',
  color: Colors.redAccent,
);
```

---

## Example Dishes

| Dish | Image File | Price (VNĐ) |
|------|-------------|-------------|
| Phở bò | `phobo.webp` | 45,000 |
| Bún chả | `buncha.webp` | 40,000 |
| Bún bò | `bunbo.jpg` | 45,000 |
| Cơm tấm | `comtam.jpg` | 35,000 |

---

## UI Overview

| Component | Description |
|------------|-------------|
| **AppBar** | Displays app title “🍜 Menu 🍜”. |
| **Drawer** | Navigation categories for dishes. |
| **Body** | Displays menu cards (grid or column layout). |
| **FAB (FloatingActionButton)** | Simulates placing an order with a SnackBar confirmation. |

---

## Sample UI

**Mobile Layout**
```
🍜 Menu 🍜
-------------------
🍽️ Today's Menu 🍽️
[Phở bò]
[Bún chả]
[Bún bò]
[Cơm tấm]
```

**Tablet Layout**
```
🍜 Menu 🍜
-------------------
🍽️ Today's Menu 🍽️
[Phở bò] [Bún chả]
[Bún bò] [Cơm tấm]
```

---

## Installation & Run

### Prerequisites
- Flutter SDK installed
- Android Studio / VS Code

### Steps
```bash
git clone https://github.com/your-username/flutter-food-menu.git
cd flutter-food-menu
flutter pub get
flutter run
```

---

## Assets Setup

Place your images inside:
```
assets/images/
├── phobo.webp
├── buncha.webp
├── bunbo.jpg
└── comtam.jpg
```

Then, declare them in your `pubspec.yaml`:
```yaml
flutter:
  assets:
    - assets/images/
```

---

## Future Improvements

- Add real-time cart system  
- Connect to Firebase for menu updates  
- Support dark mode  
- Multi-language support (EN/VN)

---

## Author

**Created by:** Dang Bach Tran 
**Language:** Dart  
**Framework:** Flutter  
**Version:** 3.x  

---

> 🍜 *Enjoy coding — and your meal!* 🍜
