# Quizimals - Educational Animal Quiz Game Template For Android (Python & Kivy)

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/hero.png)

---

## Table of Contents
1. [Introduction](#1-introduction)
2. [System Requirements](#2-system-requirements)
3. [Getting Started](#3-getting-started)
4. [Project Structure](#4-project-structure)
5. [Core Components](#5-core-components)
6. [Game Mechanics](#6-game-mechanics)
7. [Customization Guide](#7-customization-guide)
8. [To-Do and Limitations](#8-to-do-and-limitations)
9. [Performance Considerations](#9-performance-considerations)
10. [Support and Contact](#10-support-and-contact)
11. [Attributions](#11-attributions)
12. [FAQs](#12-faqs)
13. [Troubleshooting](#13-troubleshooting)
14. [License Information](#14-license-information)

## 1. Introduction
Quizimals is an interactive educational app designed to help children learn animal names through an engaging game format. Players are presented with animal images and scrambled letters, challenging them to spell the correct animal name. Built using Python and Kivy, this template is highly customizable and provides an excellent starting point for developers interested in creating educational quiz apps. The app is ready to be converted into an Android APK and comes with a pre-configured setup for easy deployment using GitHub Actions.

### 💡 Learning Outcomes

- 👂 Improve listening and pronunciation with audio for each animal
- ✍️ Boost spelling and vocabulary through word puzzles
- 🧠 Encourage visual recognition and memory via flashcard collection
- 🎯 Support progress tracking through category unlocks

### ✨ Key Features

- 🎮 **Fully Functional Game Flow** – Welcome, category, quiz, album, and reward screens
- 🐒 **Animal Album** – Unlock and listen to flashcards with native pronunciation
- 🧩 **Scrambled Letter Challenges** – Interactive spelling mechanic with hints
- 💰 **Coin & Reward System** – Earn coins, buy hints, and collect daily rewards
- 🌍 **5 Animal Environments** – Jungle, Sea, Savanna, Forest, and Farm
- 🛠️ **Easy to Customize** – Replace assets or extend with new categories and themes
- 📱 **Android-Ready** – Comes with buildozer.spec and GitHub Actions config for APK builds

### 🎯 Perfect For:

- Educational app developers
- Game dev students & indie creators
- Teachers building fun classroom tools
- Anyone looking to sell or ship engaging quiz apps

## 2. System Requirements

- Python 3.11.11
- Kivy 2.3.1
- Kivymd https://github.com/kivymd/KivyMD/archive/master.zip
- materialyoucolor
- exceptiongroup
- asyncgui
- asynckivy
- sqlite3

## 3. Getting Started

1. Download the template from my [Ko-Fi shop](https://ko-fi.com/s/e59f5b48b6).
2. Unzip the downloaded file to your preferred development directory
3. Install the required dependencies (Python, Kivy, KivyMD, and sqlite3).
4. Review the project structure and familiarize yourself with the core components.
5. Customize the game content using the guide in [Section 7](#7-customization-guide).
6. Test the game thoroughly on various Android devices.
7. Use the provided `buildozer.spec` file and `.github/workflows/build.yml` to build the Android APK.

## 4. Project Structure
```
root/
│
├── main.py                     # Main entry point
├── main.kv                     # Main kivy file
├── buildozer.spec              # Android build config
├── icon.png                    # App icon
├── presplash.png               # Loading splash screen
│
├── .github/                    # GitHub Actions config
│   └── workflows/
│      └── build.yml            # APK build workflow
│
├── utils/
│   ├── database_utils.py       # Database operations
│   ├── utils.py                # Utility functions
│   └── game_state.py           # Manages global game state
│
├── assets/                     # Game resources
│   ├── fonts/                  # Custom fonts
│   ├── audio/                  # Sound files
│   │   ├── pronunciation/      # Animal name pronunciations
│   │   ├── sfx/                # Sound effects
│   │   └── ui/                 # Interface sounds
│   │
│   ├── images/                 # Small colored & gray scalled animals images for album
│   ├── album/                  # Album card images
│   │   ├── farm/               # Farm animal album images
│   │   ├── savanna/            # Savanna animal album images
│   │   ├── forest/             # Forest animal album images
│   │   ├── jungle/             # Jungle animal album images
│   │   └── sea/                # Sea animal album images
│   │
│   ├── quiz/                   # Medium size colored animals images
│   │   ├── farm/               # Farm animal quiz images
│   │   ├── savanna/            # Savanna animal quiz images
│   │   ├── forest/             # Forest animal quiz images
│   │   ├── jungle/             # Jungle animal quiz images
│   │   └── sea/                # Sea animal quiz images
│   │
│   ├── animations/             # Animation resources
│   │   └── light/              # Light animation frames
│   │
│   └── ui/                     # UI assets
│       ├── backgrounds/        # Background images
│       ├── buttons/            # Button images
│       ├── icons/              # Icon images
│       ├── layouts/            # Layout images
│       └── popups/             # Popup panel images
│
└── app/                        # Application code
    ├── screens/                # Game screens
    │   ├── welcomescreen/      # Welcome screen files
    │   ├── loadscreen/         # Loading screen files
    │   ├── menuscreen/         # Main menu screen files
    │   ├── categoryscreen/     # Category selection screen files
    │   ├── albumscreen/        # Animal album screen files
    │   └── quizscreens/        # Quiz screens for categories
    │       ├── farmscreen.py   # Farm animals quiz
    │       ├── savannascreen.py # Savanna animals quiz
    │       ├── forestscreen.py # Forest animals quiz
    │       ├── junglescreen.py # Jungle animals quiz
    │       └── seascreen.py    # Sea animals quiz
    │
    ├── customwidgets/          # Custom UI components
    │   ├── custombuttons/      # Custom button classes
    │   ├── customlayouts/      # Custom layout classes
    │   ├── customlabels/       # Custom label classes
    │   ├── customprogressbar.py # Progress bar component
    │   └── custompopups.kv     # Popup designs
    │
    ├── components/             # Reusable components
    │   ├── basescreen/         # Base screen class
    │   └── flashcard/          # Flashcard component for album
    │
    └── animations/             # Animation logic
        └── animation.py        # Win animations
```

## 5. Core Components
### 5.1 Main Files
- `main.py`: Entry point of the app.
- `main.kv`: The main Kivy file that defines the app's structure.
- `buildozer.spec`: Build configuration for Android APK.
- `icon.png`: Icon of the application.
- `presplash.png`: Image used as presplash.

### 5.2 Database and Utilities
- `database_utils.py`: Handles database operations for storing and retrieving game data.
- `utils.py`: Contains utility functions used throughout the app.
- `game_state.py`: Manages global game state including coins and hints.

### 5.3 Screens
- `welcomescreen`: Initial application screen presenting brand identity and launch control.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/welcome-screen.jpg)

- `loadscreen`: Loads necessary data and resources as the app starts, ensuring a smooth user experience.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/load-screen.jpg)

- `menuscreen`: The central hub of the app, featuring a daily reward system that keeps users engaged and coming back daily.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/menu-screen.jpg)

- `categoryscreen`: Screen for displaying and managing categories of questions in the game.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/category-screen.jpg)

- `quizscreens`: Individual quiz screens for each animal category:

  - `farmscreen.py`: Quiz screen for farm animals.
  
  ![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/farm-screen.jpg)

  - `savannascreen.py`: Quiz screen for savanna animals.
  
  ![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/savanna-screen.jpg)

  - `forestscreen.py`: Quiz screen for forest animals.
  
  ![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/forest-screen.jpg)

  - `junglescreen.py`: Quiz screen for jungle animals.
  
  ![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/jungle-screen.jpg)

  - `seascreen.py`: Quiz screen for sea animals.
  
  ![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/sea-screen.jpg)

- `shopscreen`: In-game store interface for purchasing hint power-ups using collected coins.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/shop-screen.jpg)

- `albumscreen`: Collection of unlocked animals with pronunciation and information.

![](https://github.com/OuchenTech/Quizimals-documentation/blob/main/screenshots/album-screen.jpg)

### 5.4 Components
- `basescreen`: Base screen classes for game screens.
- `flashcard`: Reusable flashcard component for the album feature.

### 5.5 Custom Widgets
- `custombuttons`: Custom buttons logic and design.
- `customlayouts`: Custom layouts logic and design.
- `customlabels`: Custom labels for various text elements.
- `customprogressbar.py`: Visual progress tracking component.
- `custompopups.kv`: Pop-ups design for the UI.

### 5.6 Animations
- `animation.py`: Logic for light animations diplayed after completing a category.

### 5.7 Assets
- `fonts/`: Custom fonts used in the app.
- `audio/`: Sound files including:
  - `pronunciation/`: Animal name audio pronunciations.
  - `sfx/`: Game sound effects.
  - `ui/`: Interface interaction sounds.
- `images/`: App Images:
  - `album/`: Category-specific animal images for album cards.
  - `quiz/`: Category-specific animal images for quiz screens.
  - `animations/light/`: Animation frame sequences.
  - `ui/`: Interface assets including backgrounds, buttons, icons, layouts, and popup panels.

### 5.8 Github Actions
- `.github/workflows/build.yml`: GitHub Actions APK building.

## 6. Game Mechanics
### 6.1 Gameplay
The game follows these basic mechanics:
1. Players select an unlocked category of animals.
2. An animal image is displayed along with scrambled letters.
3. Players use letter buttons to spell the animal's name.
4. Correct answers award coins.
5. Hints (add letter, remove letter, clear letter) are available for assistance.

### 6.2 Hint System
Three types of hints are available:
1. `Add Letter`: Adds a correct letter to the answer.
2. `Remove Letter`: Removes a letter that is not part of the correct word.
3. `Clear Letter`: Removes the last added letter (clear mistakes).

### 6.3 Category Progression
A new category is unlocked when the player answers all questions in the current category.

### 6.4 Animal Album
The album feature allows players to:
1. View a collection of animals they've encountered in quizzes.
2. Access flashcards with animal images and names.
3. Unlock locked animal cards using in-game coins.
4. Listen to pronunciation of animal names.

## 7. Customization Guide
### 7.1 Adding a New Animal to an Existing Category
1. In `database_utils.py`, add the new animal data to the `animals_data` list:
   ```python
   (animal_name, "CORRECT_ANSWER", "unanswered", "category_name", "locked")
   ```
   For example:
   ```python
   ("goose", "GOOSE", "unanswered", "farm", "locked")
   ```

2. Add animal images in multiple sizes:
   - Quiz image: `assets/quiz/[category_name]/[animal_name].png` (medium size (256px*256px) colored image)
   - Album image:
     - `assets/album/[category_name]/[animal_name]-rs.png` (small size (100px*100px) colored image)
     - `assets/album/[category_name]/[animal_name]-gs.png` (small size (100px*100px) grayscaled image)

3. Add pronunciation audio file:
   - `assets/audio/pronunciation/[animal_name].mp3`

4. Ensure all filenames exactly match the animal name in lowercase.

### 7.2 Creating a New Category
1. In `database_utils.py`, add a new list of animal data for the category in `animals_data`:
   
   For example:
   ```python
   ("camel", "CAMEL", "unanswered", "desert", "locked"),
   ("jerboa", "JERBOA", "unanswered", "desert", "locked"),
   ("meerkat", "MEERKAT", "unanswered", "desert", "locked"),
   ```

2. In `database_utils.py`, add the new animal data to the `categories_data` list:
   ```python
   (category_name, category_title, category_primary_color, lock_value)
   ```
   For example:
   ```python
   ("desert", "Creatures of the Enchanted Oasis", "#e3c78a", 0)
   ```

3. Create necessary asset folders:
   - `assets/quiz/desert/`
   - `assets/album/desert/`
   - Add animal images to both folders (medium-sized colored images for quiz, smaller colored and grayscaled for album).

4. Add pronunciation audio files:
   - `assets/audio/pronunciation/camel.mp3`
   - `assets/audio/pronunciation/jerboa.mp3`
   - `assets/audio/pronunciation/meerkat.mp3`

5. For the new category UI:
   - Generate a background image: `assets/ui/backgrounds/desert.jpg` or `.png`
   - Create or reuse layout image for the new category from `assets/ui/layouts/`
   - Create or reuse button image for the new category from `assets/ui/buttons/`

6. In `categoryscreen.kv`, add a new `CategoryCard` widget with an id = `[categoryname]_animals_card`:

   ```kivy
   CategoryCard:
       id: desert_animals_card
       pos_hint: {'center_x': .5, 'center_y': .5}
   ```

7. Create a new quiz screen in the `app/screens/quizscreens/` folder:
   - `desertscreen.py`

8. Template for the new quiz screen python file (`desertscreen.py`):
   ```python
   """
   Desert Screen Module for Quizimal Game

   Implements the desert animal category quiz screen.
   """

   from app.components.basescreen.basescreen import QuizScreen
   from kivy.properties import StringProperty, ColorProperty

   class DesertScreen(QuizScreen):
       """
       Quiz screen for desert animal category.
       
       Inherits all quiz functionality from QuizScreen with desert-specific:
       - Background image
       - Category styling
       - Animal questions
       
       Attributes:
           background_image (StringProperty): Desert background image path
           animal_category (StringProperty): Category identifier ('desert') 
           category_color (ColorProperty): Primary desert color (#e3c78a)
           category_background_color (ColorProperty): Secondary desert color (#d4b87a)
       """
       
       background_image = StringProperty("assets/ui/backgrounds/desert.jpg")
       animal_category = StringProperty("desert")
       category_color = ColorProperty("#e3c78a")
       category_background_color = ColorProperty("#d4b87a")
       
       def __init__(self, **kwargs):
           """
           Initialize desert screen.
           """
           super(DesertScreen, self).__init__(**kwargs)
           
       def on_pre_enter(self, *args):
           """
           Called before screen display.
           
           Actions:
           - Loads current game elements
           """
           self.load_elements()
           
       def on_pre_leave(self, *args):
           """
           Called before screen exit.
           
           Actions:  
           - Updates category progress in category screen
           """
           self.manager.get_screen("category_screen").update_category_progress(self.animal_category)
   ```

9. In `loadscreen.py`:
    - Inside `lazy_load_screen function()`, add the new screen class to `screen_map` list.
    ```python
    from app.screens.quizscreens.desertscreen import DesertScreen
    ```
    
    - Add the screen widget in `lazy_load_screen()` method:
    ```python
    'desert_screen': 'app.screens.quizscreens.desertscreen.DesertScreen',
    ```
    
    - Increase the number of tasks in `self.total_tasks`
    
    - Create functions to load screen data of the new category:
    ```python
    def load_desert_screen(self):
        # Loading desert screen
        self.lazy_load_screen("desert_screen")
        desert_screen = self.manager.get_screen("desert_screen")
        self.run_method(desert_screen.preload_sounds, self.on_desert_sounds_loaded)

    def on_desert_sounds_loaded(self, dt):
        #Desert sounds loaded
        desert_screen = self.manager.get_screen("desert_screen")
        self.run_method(desert_screen.create_question_ui, self.on_desert_ui_created)

    def on_desert_ui_created(self, dt):
        # Desert UI created
        desert_screen = self.manager.get_screen("desert_screen")
        self.run_method(desert_screen.load_questions_list, self.on_desert_screen_loaded)

    def on_desert_screen_loaded(self, dt):
        # desert screen loaded
        self.update_progress()
        self.load_next_screen()
    ```

### 7.3 Album Configuration
1. To ensure a new animal appears in the album:
   - Ensure the animal is in the database with proper card_state
   - Create album-sized images in the album folder
   - Add pronunciation audio files
   - Update the album screen will automatically include the new animal when browsing through pages

2. Album customization options:
   - Modify the FlashCard appearance in `app/components/flashcard/`
   - Adjust pagination settings in `albumscreen.py` by changing the grid layout parameters
   - Change unlock costs by modifying the coin values in the unlock_the_card method

### 7.4 Customizing Widgets
1. Custom Buttons:
   - Locate the `CustomButton` class in `custombuttons.py` and `custombuttons.kv`
   - Modify the `background_normal` and `background_down` properties to change the button's appearance

2. Custom Layouts:
   - Find the `CustomLayout` class in `customlayouts.py` and `customlayouts.kv`
   - Change the `background` property to use a different background image

3. Custom Labels:
   - Edit the `CustomLabel` class in `customlabels.py` and `customlabels.kv`
   - Customize the `font_name`, `font_size`, and `color` properties

4. Custom Panels:
   - Open `custompopups.kv`
   - Modify the `Image` class to change the panel's background image
   - Adjust the `size_hint` and `pos_hint` to change the panel's size and position

5. Creating New Custom Widgets:
   - Create a new Python file in the `customwidgets` folder (e.g., `customslider.py`)
   - Define your custom widget class, inheriting from an appropriate Kivy widget
   - Create a corresponding `.kv` file if needed (e.g., `customslider.kv`)
   - Include the `.kv` file in `main.kv`
   - Import and use your new custom widget in the relevant screens

Remember to test your customizations thoroughly to ensure they work well across different screen sizes and maintain the game's performance.

## 8. To-Do and Limitations
1. Assets Customization:
   - While the UI assets provided are free to use, developers may need to replace them with their own assets to suit their specific game theme or branding.
   - Background images are currently generated using AI tools and have a fixed aspect ratio. To ensure compatibility across various device screen sizes, developers should generate their own background images with different aspect ratios.

2. Multi-word Animals:
   - The current template is designed to handle single-word animal names only.
   - If you plan to include animals with multiple words in their names, you'll need to modify the code accordingly.

3. Localization:
   - Consider adding support for multiple languages to reach a broader audience.
   - Pronunciation audio files would need to be created for each language.

4. Album Enhancements:
   - Add more detailed animal information cards.
   - Implement animal sounds in addition to name pronunciations.
   - Add "favorite" feature to bookmark special animals.

5. Additional Categories:
   - Expand the game by adding more animal categories or entirely new themes (e.g., plants, countries, etc.).

## 9. Performance Considerations
To ensure smooth performance on both lower-end and high-end devices, the following optimization techniques have been implemented:

Key Optimization Techniques:

1. Background Data Loading (Threading)
   - Heavy tasks like database operations and resource loading are run in background threads.
   - Images and sounds are loaded asynchronously to prevent UI blocking.
   - Benefit: Prevents UI freezing, ensuring smoother performance on lower-end devices.

2. Simple Welcome Screen for Fast Startup
   - A lightweight WelcomeScreen is shown immediately after the presplash to avoid delays.
   - Benefit: Reduces startup time and avoids black screens between presplash and first screen.

3. Lazy Screen Loading
   - Screens are loaded only when needed using the lazy_load_screen function, reducing initial memory usage and load time.
   - Benefit: Faster startup and reduced memory consumption, especially on low-end devices.

4. Dynamic Progress Updates
   - The loading process updates the progress label percentage in real time as tasks are completed.
   - Benefit: Keeps users informed, improving user experience.

5. Efficient Database Access
   - Database operations are minimized and batched to reduce the number of queries.
   - Benefit: Faster performance, particularly on devices with slow I/O.

6. Image and Sound Preloading
   - Quiz images and sounds are preloaded in the background to ensure smooth transitions.
   - Benefit: Prevents lags or frame drops during gameplay.

7. Incremental Album Rendering
   - The album screen loads flashcards incrementally with pagination.
   - Cards are rendered with small delays between each to maintain interface responsiveness.
   - Benefit: Album remains responsive even with many flashcards.

8. Reused UI Components
   - UI components (e.g., quiz buttons, flashcards) are reused across screens and dynamically updated.
   - Benefit: Reduces widget creation overhead, saving memory and improving performance.

9. Cache Management
   - The album screen implementation uses page caching to reduce redundant widget creation.
   - Benefit: Faster navigation between album pages after initial loading.

## 10. Support and Contact
For support or inquiries about the Quizimals game template, please contact us through:

- Email: ouchen.yassine.umi@gmail.com
- Discord: ouchentech

We strive to respond to all inquiries within 48 hours. Please provide as much detail as possible about your issue or question to help us assist you more effectively.

## 11. Attributions
We would like to acknowledge the following resources used in the Quizimals game template:

- Sound Effects: Ultimate UI SFX Pack by JDSherbert 
  (https://jdsherbert.itch.io/ultimate-ui-sfx-pack)
- Buttons and Layouts: UI Light by Wenrexa 
  (https://wenrexa.itch.io/uilight)
- Pop-ups: Casual GUI for Cooking Game by Lraien 
  (https://lraien.itch.io/casual-giu-for-cooking-game)
- Animal Images: Tigatelu on Vecteezy 
  (https://www.vecteezy.com/members/tigatelu)
- Icons: Various artists on Flaticon 
  (https://www.flaticon.com/)
- Pronunciation Audio: Generated with text-to-speech technology

We are grateful to these creators for their excellent resources that have contributed to the visual and audio quality of this template.

Note: Developers are responsible for ensuring they have the necessary rights and licenses for any assets (images, sounds, etc.) they use in their final product.

## 12. FAQs
1.
- **Q**: Can I resell the template?
- **A**: No, you can't resell the template as it is. The license allows you to use the template to create and sell your own games, but you cannot redistribute or resell the template itself.

2.
- **Q**: Can I use this template for commercial projects?
- **A**: Yes, you can use this template to create commercial projects. However, make sure you have the necessary rights for any assets you use in your final product.

3.
- **Q**: Do I need to credit the original template in my game?
- **A**: While not required, we appreciate if you include a credit to the Quizimals template in your game's credits or about section.

4.
- **Q**: Can I modify the template code?
- **A**: Yes, you are encouraged to modify and customize the template code to fit your needs. That's what it's designed for!

5.
- **Q**: Is this template suitable for beginners?
- **A**: While some familiarity with Python and Kivy is beneficial, the template is designed to be accessible to developers of various skill levels. The documentation provides guidance for customization and expansion.

6.
- **Q**: How do I add animals to the album?
- **A**: Animals are automatically added to the album when their data is added to the database. Make sure to add images to both quiz and album folders, and provide pronunciation audio files.

7.
- **Q**: Can I change the coin cost for unlocking album cards?
- **A**: Yes, modify the coin cost in the `unlock_the_card` method in the `albumscreen.py` file.

## 13. Troubleshooting
1.
- **Issue**: The app crashes on startup
- **Solution**: Ensure all dependencies are correctly installed and up to date. Check the error log for specific issues.

2.
- **Issue**: Images or sounds are not loading
- **Solution**: Verify that all asset files are in the correct directories and named correctly. Check file permissions.

3.
- **Issue**: The app is slow or laggy
- **Solution**: Review the Performance Considerations section. Ensure you're not loading too many high-resolution images at once.

4. 
- **Issue**: Buildozer fails to create APK
- **Solution**: Make sure you have the latest version of Buildozer installed. Check the build log for specific errors and ensure all required Android SDK components are installed.

5.
- **Issue**: Custom fonts are not working
- **Solution**: Ensure the font files are correctly placed in the `assets/fonts` directory and that you're referencing them correctly in your .kv files.

6.
- **Issue**: Animal pronunciations not playing
- **Solution**: Check that audio files exist in the correct location (`assets/audio/pronunciation/`) and that the filename matches the animal name exactly.

7.
- **Issue**: Album cards not appearing
- **Solution**: Verify that animal data exists in the database with correct card states and that corresponding album images exist.

If you encounter any issues not covered here, please reach out to our support team via the contact methods provided in the Support and Contact section.

## 14. License Information

### 14.1 License Terms

**Quizimals** is released under a Commercial Template License. This license is designed to give developers flexibility while protecting the original work from unauthorized redistribution.

This license allows you to:
- Create multiple end products (personal or commercial applications) from a single license purchase
- Modify the template code for your own projects
- Sell or distribute applications created using this template
- Modify and resell the template as part of a substantially different product with proper attribution

The following restrictions apply:
- You may not resell or redistribute the original unmodified template
- You may not include the template in developer toolkits or template collections
- You may not claim the template design or code as your own original work

### 14.2 Commercial Template License Text

```
Quizimals Commercial Template License

Copyright (c) 2025 OuchenTech

This license grants the purchaser a non-exclusive right to use the Quizimals template under the following terms:

1. USAGE RIGHTS:
   - The purchaser may use the template to create unlimited end products for personal use or for clients.
   - Each end product may be sold or distributed without additional licensing fees.

2. REDISTRIBUTION RESTRICTIONS:
   - The original unmodified template may not be resold, redistributed, or included in template collections.
   - The template code may not be used to create a competing template product similar to Quizimals.

3. MODIFICATION RIGHTS:
   - The purchaser may modify the template for their own projects.
   - Substantially modified versions of the template may be resold as new products, provided they include significant changes or additions that transform it from the original.
   - Any resold modified version must include attribution to OuchenTech as the original creator in the documentation and about section.

4. ATTRIBUTION:
   - Attribution is not required in end products but is appreciated.
   - Attribution is required when reselling modified versions of the template.

5. WARRANTY:
   THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

---

© *OuchenTech 2025*
