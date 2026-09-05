# Energy Consumption Prediction

A **Flutter mobile application** that predicts energy consumption for all Indian states using **Random Forest Regression** (95%+ accuracy). Built as a college project with a Python Flask backend and ML pipeline.

## Features

- **State-wise Prediction** — Predicts energy consumption for all 37 Indian states/UTs
- **Multi-parameter Input** — Region, power category, fuel type, month, year, sub-category
- **Random Forest Model** — 95%+ accuracy on historical energy data
- **Data Visualization** — Graphical energy trend representations
- **User-Friendly UI** — Intuitive dropdowns with Lottie animations

## How It Works

1. User selects parameters (state, region, fuel type, month, year)
2. Flutter app sends JSON request to Flask backend via ngrok
3. Flask API runs Random Forest prediction model
4. Result returned and displayed in the app

## Quick Start

### Frontend (Flutter)

```bash
git clone https://github.com/ayusharyan1309/energy_consuption_prediction.git
cd energy_consuption_prediction
flutter pub get
flutter run
```

### Backend (Flask ML API)

The Flask backend runs separately and is exposed via ngrok. Update the URL in `lib/homePage.dart`:

```dart
final ngrokUrl = "https://your-ngrok-url.ngrok-free.app";
```

## Input Parameters

| Parameter | Options |
|-----------|---------|
| **State** | 37 Indian states/UTs (Andhra Pradesh, Bihar, Delhi, etc.) |
| **Region** | South, East, North, West, Central, N/A |
| **Power Category** | Electricity generation, Power sector emissions, Other |
| **Variable** | Clean, Fossil, Coal, Gas, Hydro, Nuclear, Solar, Wind, etc. (18 types) |
| **Sub-Category** | Aggregate fuel, Fuel, Total, CO2 intensity |
| **Month** | January - December |
| **Year** | 2019 - 2030 |

## Project Structure

```
lib/
├── main.dart                    # App entry point
├── splashScreen.dart            # Lottie animation splash
├── homePage.dart                # Main prediction form + API call
└── widgets/
    ├── mappingInputs.dart       # All dropdown mapping constants
    ├── stateDropDown.dart       # Indian states dropdown
    ├── regionDropDown.dart      # Region selection
    ├── powerCategory.dart       # Power category dropdown
    ├── variable.dart            # Fuel/variable type dropdown
    ├── subCategoryDropdown.dart # Sub-category dropdown
    ├── selectMonth.dart         # Month picker
    └── yearDropDown.dart        # Year picker (2019-2030)
```

## Tech Stack

| Component | Technology |
|-----------|------------|
| **Frontend** | Flutter, Dart |
| **State Management** | GetX |
| **Backend** | Python Flask + ngrok |
| **ML Algorithm** | Random Forest Regression |
| **ML Libraries** | Scikit-learn, Pandas, NumPy |
| **Animations** | Lottie |

## ML Model

- **Algorithm**: Random Forest Regression
- **Accuracy**: 95%+
- **Training Data**: Historical energy consumption data for Indian states
- **Features**: State, region, power category, fuel type, month, year, sub-category
- **Target**: Energy consumption value (in appropriate units)
