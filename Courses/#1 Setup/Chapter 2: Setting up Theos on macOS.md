# Chapter 2: Setting up Theos on macOS

Let’s install Theos on macOS. If you’re using Linux or Windows with WSL, you can skip to the next tutorial.

> **Hint**:<br/>
> You can find Theos documentation here: https://theos.dev/docs/installation-macos.<br/>
> You can find Xcode on the App Store here: https://apps.apple.com/app/id497799835.<br/>
> You can find Xcode on the Developer Portal here: https://developer.apple.com/downloads/applications/.<br/>
> You can find Homebrew here: https://brew.sh.

Visit the Theos documentation for macOS on your web browser. The documentation already tells us all we need to do. First we need to install some dependencies. If you already have Xcode and Homebrew installed, you can skip ahead.

I'll be downloading Xcode from the Developer Portal. For this, we'll need to sign in with any Apple ID. I'll download the latest release version of Xcode here. With the download complete, simply double click to extract the archive. We now have Xcode. You can move Xcode into your Applications folder, but that's not needed. Go ahead and open Xcode. When you open a recent version of Xcode for the first time, you may see a screen asking if you would like to download additional resources. You don't need to download any of these to use Theos. If you would like to download them later, you can do that too.

We'll now install Homebrew. This process is very straight-forward. Copy the installer command from the documentation and paste it into Terminal. Press return to confirm.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Great! We're now ready to install Theos. Run the install command from the documentation to install Theos:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/theos/theos/master/bin/install-theos)"
```

This command will now install additional dependencies. This requires entering your password.
You can see Theos installing to your home directory.
Lastly, the installer extracts the latest SDKs.

We have one last tool to install. We'll install a newer version of `make`:

```bash
brew install make
```

This version of `make` is faster than the version that Xcode provides.
To make sure you use this version of `make`, we'll run

```bash
echo 'export PATH="$(brew --prefix make)/libexec/gnubin:${PATH}"' >> ~/.zprofile
```

We'll now re-start the shell. This is important for the Theos installation to complete and the changes for `make` to take effect.

Now you're ready to use Theos on macOS!
