# my-luncher
┌───────────────────────────────────────────────────────────────────────────┐
│                         Android System & Hardware                         │
│  PackageManager · CameraManager (Torch) · AudioManager · BatteryManager   │
│  Contacts Provider · StatFs · Photo Picker · Open-Meteo Weather API       │
└───────────────────────────────┬───────────────────────────────────────────┘
                                │
                                ▼
┌───────────────────────────────────────────────────────────────────────────┐
│                         Data & System Repositories                        │
│  ┌──────────────────────┐  ┌──────────────────────┐  ┌─────────────────┐  │
│  │   AppRepository      │  │ SystemControlRepo    │  │ WeatherRepo     │  │
│  │ (Async Icon Cache,   │  │ (Torch, Brightness,  │  │ (Open-Meteo +   │  │
│  │  Categories, Search) │  │  Volume, Battery)    │  │  City Geocoding)│  │
│  └──────────┬───────────┘  └──────────┬───────────┘  └────────┬────────┘  │
│             └─────────────────────────┼───────────────────────┘           │
│                                       ▼                                   │
│                        ┌─────────────────────────────┐                    │
│                        │   LauncherPreferencesStore  │                    │
│                        │   (DataStore + JSON Layout) │                    │
│                        └──────────────┬──────────────┘                    │
└───────────────────────────────────────┼───────────────────────────────────┘
                                        │
                                        ▼
┌───────────────────────────────────────────────────────────────────────────┐
│                        LauncherViewModel (MVVM)                           │
│   StateFlow<LauncherUiState> · SuperIslandState · ControlCenterState      │
│   SpotlightSearchState · EditModeState · Predictive Back Stack            │
└───────────────────────────────────────┬───────────────────────────────────┘
                                        │
                                        ▼
┌───────────────────────────────────────────────────────────────────────────┐
│                      Jetpack Compose Launcher Shell                       │
│  ┌───────────────────┐  ┌─────────────────┐  ┌─────────────────────────┐  │
│  │   Super Island    │  │   Home Pager    │  │     Floating Dock       │  │
│  │ (Timer/Music/Chg) │  │ Widgets + Pages │  │  Pinned + Search Pill   │  │
│  └───────────────────┘  │ + App Library   │  └─────────────────────────┘  │
│                         └─────────────────┘                               │
│  ┌─────────────────────────────────────────────────────────────────────┐  │
│  │  Animated Overlays (Backdrop Blur + Spring Physics + BackHandler)   │  │
│  │  · App Drawer (A-Z Rail)       · Quick Control Center               │  │
│  │  · Spotlight Search            · Wallpaper / Edit / Settings Sheets │  │
│  └─────────────────────────────────────────────────────────────────────┘  │
└───────────────────────────────────────────────────────────────────────────┘
