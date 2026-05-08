# 👨‍🎓 Список студентов (Student List)

[![Platform](https://img.shields.io/badge/Platform-Android-blue.svg)](https://developer.android.com)
[![Compose](https://img.shields.io/badge/Jetpack-Compose-4285F4.svg)](https://developer.android.com/jetpack/compose)
[![Material](https://img.shields.io/badge/Material-Design%203-006C4C.svg)](https://m3.material.io)
[![Kotlin](https://img.shields.io/badge/Kotlin-1.9+-blue.svg)](https://kotlinlang.org)

> 📚 Учебное приложение, демонстрирующее применение принципов **Material Design 3** в Android-приложениях с использованием **Jetpack Compose**.

---

## 🎯 Цель работы

Научиться применять принципы Material Design в Android-приложениях:

- ✅ Цветовые схемы (Light/Dark темы)
- ✅ Типографика с кастомными шрифтами (Montserrat, Abril Fatface)
- ✅ Формы и скругления компонентов (Shape)
- ✅ Анимации и интерактивные элементы (Spring Animation)
- ✅ Создание адаптивного интерфейса с Scaffold и TopAppBar

---

## ✨ Функциональность

| Функция | Описание |
|---------|----------|
| 📋 Список студентов | Отображение 10 студентов с аватарками, именами и возрастом |
| 🎨 Кастомная тема | Зелёная цветовая схема (#006C4C) для светлой и тёмной тем |
| 🌙 Тёмная тема | Автоматическая адаптация под системную тему Android |
| 🔤 Кастомные шрифты | Abril Fatface для заголовков, Montserrat для основного текста |
| ⭕ Круглые аватарки | Обрезка изображений через `ContentScale.Crop` и `clip()` |
| 📐 Скруглённые карточки | Диагональное скругление углов (topEnd + bottomStart) |
| 🔽 Раскрытие описания | Анимированное раскрытие/сворачивание карточки с описанием |
| 📱 Top App Bar | Верхняя панель с логотипом и названием приложения |
| ♻️ Адаптивность | Корректные отступы через `contentPadding` в Scaffold |

---

## 🛠️ Технологии и зависимости

### Основные технологии

| Технология | Версия | Назначение |
|-----------|--------|------------|
| **Jetpack Compose** | Latest | Declarative UI для Android |
| **Material Design 3** | Latest | Дизайн-система Google |
| **Kotlin** | 1.9+ | Язык разработки |
| **Android SDK** | API 25+ | Минимальная версия Android |

### Зависимости проекта (`build.gradle.kts`)

```kotlin
dependencies {
    // Jetpack Compose
    implementation(platform("androidx.compose:compose-bom:2024.04.01"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.ui:ui-graphics")
    implementation("androidx.compose.ui:ui-tooling-preview")
    implementation("androidx.compose.material3:material3")
    
    // Иконки для анимации раскрытия
    implementation("androidx.compose.material:material-icons-extended:1.6.0")
    
    // Activity Compose
    implementation("androidx.activity:activity-compose:1.9.0")
    
    // Тестирование
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.compose.ui:ui-test-junit4")
}
```

---

## 🗂️ Структура проекта

```
app/
├── src/main/
│   ├── java/com/example/sda_material_design/
│   │   ├── MainActivity.kt          # Основной экран, Composable-функции
│   │   ├── data/
│   │   │   ├── Student.kt           # Data class модели студента
│   │   │   └── DataSource.kt        # Список студентов
│   │   └── ui/theme/
│   │       ├── Color.kt             # Цветовая схема (Light/Dark)
│   │       ├── Shape.kt             # Формы компонентов (RoundedCornerShape)
│   │       ├── Theme.kt             # Тема приложения (MaterialTheme)
│   │       └── Type.kt              # Типографика (FontFamily, TextStyle)
│   ├── res/
│   │   ├── drawable/                # Иконки и изображения студентов
│   │   │   ├── ic_student_logo.xml  # Логотип приложения
│   │   │   └── student[1-10].jpg    # Аватарки студентов
│   │   ├── font/                    # Кастомные шрифты
│   │   │   ├── abril_fatface_regular.ttf
│   │   │   ├── montserrat_bold.ttf
│   │   │   └── montserrat_regular.ttf
│   │   └── values/
│   │       ├── strings.xml          # Текстовые ресурсы
│   │       ├── dimens.xml           # Размеры (отступы, image_size)
│   │       └── themes.xml           # Базовая тема
│   └── AndroidManifest.xml
├── img/                             # Скриншоты для отчёта
│   ├── step5_app_running_lightTheme_ФАМИЛИЯ.png
│   ├── step6_colors_applied_ФАМИЛИЯ.png
│   ├── step7_emulator_darkTheme_ФАМИЛИЯ.png
│   ├── step8_shapes_applied_lightTheme_ФАМИЛИЯ.png
│   ├── step9_typography_applied_lightTheme_ФАМИЛИЯ.png
│   ├── step10_appBar_lightTheme_ФАМИЛИЯ.png
│   └── step11_expanded_state_lightTheme_ФАМИЛИЯ.png
└── build.gradle.kts
```

---

## 🖼️ Скриншоты

| Светлая тема | Тёмная тема | Раскрытая карточка |
|-------------|------------|-------------------|
| ![Light Theme](img/step10_appBar_lightTheme_ФАМИЛИЯ.png) | ![Dark Theme](img/step7_emulator_darkTheme_ФАМИЛИЯ.png) | ![Expanded](img/step11_expanded_state_lightTheme_ФАМИЛИЯ.png) |

> 📁 Все скриншоты этапов выполнения находятся в папке [`img/`](img/)

---

## 🚀 Запуск проекта

### Требования

- Android Studio **Giraffe** или новее
- Android SDK **API 25+**
- Эмулятор или физическое устройство с Android 7.0+

### Инструкция

1. **Откройте проект** в Android Studio
2. **Дождитесь синхронизации** Gradle
3. **Выберите устройство** в выпадающем списке
4. **Нажмите Run** ▶️ или используйте `Shift + F10`

```bash
# Или через командную строку:
./gradlew installDebug
```

### Сборка APK

```bash
# Debug APK
./gradlew assembleDebug

# Release APK
./gradlew assembleRelease
```

Готовый файл: `app/build/outputs/apk/debug/app-debug.apk`

---

## 🎨 Кастомизация

### Изменение цветовой схемы

Откройте `ui/theme/Color.kt` и измените значения цветов:

```kotlin
// Основной цвет приложения
val md_theme_light_primary = Color(0xFF006C4C)  // Зелёный
val md_theme_dark_primary = Color(0xFF6CDBAC)   // Светло-зелёный для тёмной темы
```

### Добавление нового шрифта

1. Скачайте `.ttf` файл с [Google Fonts](https://fonts.google.com)
2. Переименуйте в нижний регистр: `my_font_regular.ttf`
3. Переместите в `res/font/`
4. Добавьте в `Type.kt`:
   ```kotlin
   val MyFont = FontFamily(Font(R.font.my_font_regular))
   ```

### Изменение формы карточек

Откройте `ui/theme/Shape.kt`:

```kotlin
val Shapes = Shapes(
    medium = RoundedCornerShape(
        topEnd = 16.dp,      // Правый верхний угол
        bottomStart = 16.dp  // Левый нижний угол
        // Остальные углы = 0.dp (острые)
    )
)
```

---

## 📝 Лицензия

Учебный проект, созданный в рамках лабораторных работ №10-11 по дисциплине «Мобильная разработка».

```
© 2026 [Ваше ФИО], группа [Ваша группа]
Все права защищены.
Использование кода разрешено только в учебных целях.
```

---

## 👨‍💻 Автор

**SDA**  
Группа: **ISP-232**

> 🎓 Проект выполнен в рамках лабораторных работ №10-11 по мобильной разработке на Android с использованием Jetpack Compose и Material Design 3.

---
 
— поставьте звезду!** Это поможет другим студентам найти этот пример. 🚀🎓