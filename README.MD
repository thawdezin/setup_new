##
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 


To install CocoaPods on an M1 Mac, follow these steps:

### 1. **Open Terminal**
   - You can use the default terminal or a different shell like iTerm2 if you prefer.

### 2. **Install Homebrew (if not installed)**
   Homebrew is required to manage dependencies like Ruby, which CocoaPods relies on.

   Run this command to install Homebrew:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   Once installed, run:
   ```bash
   brew update
   ```


You should run both of these commands in your terminal to add Homebrew to your `PATH`:

1. **First command**: This adds Homebrew to your `.zprofile`, ensuring that it's added to your `PATH` every time you start a terminal session.
   ```bash
   (echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/thawdezin/.zprofile
   ```

2. **Second command**: This applies the change immediately without needing to restart your terminal.
   ```bash
   eval "$(/opt/homebrew/bin/brew shellenv)"
   ```

After running these, Homebrew will be ready to use in your terminal.

### 3. **Install Ruby**
   Apple Silicon (M1/M2) Macs require a different Ruby version than Intel Macs to run CocoaPods smoothly.

   Install a newer version of Ruby using Homebrew:
   ```bash
   brew install ruby
   ```

   Add the Ruby path to your shell configuration file (`.zshrc` if you're using zsh):
   ```bash
   echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

### 4. **Install CocoaPods**
   Once Ruby is properly installed, install CocoaPods:
   ```bash
   sudo gem install cocoapods
   ```

### 5. **Set Up CocoaPods**
   After installation, set up the CocoaPods master repository:
   ```bash
   pod setup
   ```

### 6. **Install Pods in Your Xcode Project**
   Navigate to your Xcode project directory where your `Podfile` is located, and run:
   ```bash
   pod install
   ```

### 7. **Additional Troubleshooting for M1 Macs**
   If you encounter any issues with CocoaPods installation or execution on M1, you may need to run certain commands in **Rosetta**.

   - To install the terminal with Rosetta:
     1. Go to your Applications folder.
     2. Find Terminal, right-click and select **Get Info**.
     3. Check **Open using Rosetta**.

This setup should work for installing CocoaPods on an M1 Mac!

