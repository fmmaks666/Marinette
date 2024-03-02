# Marinette

Cute, simple and open source shell

![Initialization](etc/marinette_launch.png)
![Nesca command](etc/marinette_nesca.png)
![Session Manager](etc/marinette_sm.png)

Important note: this is **NOT A REAL HACKING TOOLKIT**! This has been made, works and will work only in the game called Grey Hack!

This repository is the only place where you can get Marinette without any risks. DON'T trust in-game websites!!!




## Table of contents

1.  [Description](#description)
2.  [Features](#features)
    1.  [Present](#features-present)
    2.  [Future](#features-future)
    3.  [No time](#features-notime)
3.  [How to install?](#installation-guide)
    1.  [Unreliable, fast way](#unreliable-install)
    2.  [Reliable, slow way](#reliable-install)
4.  [How to contribute?](#contribution)
    -   [Themes](#contrib-themes)
    -   [Translations](#contrib-lang)
    -   [Bug report](#contrib-bugreport)
    -   [Features/Commands/Bug fixes/etc](#contrib-code)
5.  [Frequently Asked Questions](#faq)
6.  [Similar projects](#similar-projects)
7.  [License](#license)
8.  [Thanks and Credits](#thanks-and-credits)




## Description <a name="description"></a>

Marinette is a [Shell](https://en.wikipedia.org/wiki/Shell_(computing)) without any fancy features like [Shell Expansions](https://www.gnu.org/software/bash/manual/html_node/Shell-Expansions.html), [Shell Scripting](https://en.wikipedia.org/wiki/Shell_script), [Pipelines](https://en.wikipedia.org/wiki/Pipeline_(Unix)) and so on. I've tried to make it as simple as I could, using few to no abstractions, allowing both the end users and myself to change it programmatically if needed. And I wouldn't say I've succeeded. =D

If you're a newbie then PLEASE DON'T USE MARINETTE OR ANY OTHER PREMADE HACKING TOOL! Hack by hand first, get a grip on the game mechanics, try to code something by yourself and have fun in general!




## Features <a name="features"></a>


### Present <a name="features-present"></a>

-   Foolproof
-   Localizable and localized into different languages(The only command not localized is `ste` because I am lazy :P)
-   Session management system
-   Basic hacking functionality
-   Simple compile-time configuration
-   Stability and reliability over other(mostly proprietary) shells
-   Source leakage proof protection of backed-in sensitive user data


### Future <a name="features-future"></a>

-   Mail client
-   Wallet client
-   Vulnerability database
-   More system administration utilities


### No time(HIGHELY unlikely to be implemented!) <a name="features-notime"></a>

-   Fancy themeing
-   Runtime configuration
-   Shell expansions, scripting, pipelines, etc.




## How to install? <a name="installation-guide"></a>

There are two ways to install Marinette: Unreliable and reliable

Unreliable is unreliable because you aren't:
1.  Dynamically creating a script for making the in-game folder structure. I can easily forget to update it when doing yet another commit
2.  Changing the password of the executable, since it's iterated with sha256() 25 times and can be changed only with a script
3.  Randomly generating the identificator, which may result in identificator collision with another Marinette user

Reliable way frees yourself from these problems


### Unreliable, fast way <a name="unreliable-install"></a>

1.  Copy [marinette_installer.src](scripts/marinette_installer.src) into the Code Editor, compile and run the binary. It will create the project structure neccessary for successfull compilation
2.  Copy every source file from [src](src) into the in-game **/home/guest/Sources/Marinette/src**
3.  (Optionally) Change the stuff in **marilib.src**
    1.  Change the **Constants.identificator** to some 32 characters long string
    2.  Change the **Constants.language** to something defined in [localization.src](src/localization.src)
    3.  Change the **Constants.theme** to something defined in [themeing.src](src/themeing.src)
4.  Compile **marinette.src**. Launch Marinette with `--password marinette` parameters. Congratulations!


### Reliable, (kinda?)slow way <a name="reliable-install"></a>

1.  Download the repository to your computer
2.  From the root of the project, run **scripts/marinette_installer.py**. It'll create **marinette_installer.src**
3.  Repeat steps 1-2 from [Unreliable way](#unreliable-install)
4.  (Optionally) Change the stuff in **marilib.src**
    1.  From the root of the project, launch **scripts/hash_password.py** with the desired password. You'll get a hashed password you can set in **Constants.password**
    2.  From the root of the project, launch **scripts/identifying_signal.py**. You'll get random identificator you can set in **Constants.identificator**
    3.  Change the **Constants.language** to something defined in [localization.src](src/localization.src)
    4.  Change the **Constants.theme** to something defined in [themeing.src](src/themeing.src)
5.  Compile **marinette.src**. Launch Marinette with `--password YOUR_PASSWORD_HERE` parameters. Congratulations!




## How to contribute? <a name="contribution"></a>

There are several ways you can contribute to Marinette


### Themes <a name="contrib-themes">

Fork, put your theme inside of [themeing.src](src/themeing.src), commit and open the pull request


### Translations <a name="contrib-lang">

Want to translate 220+ locale entries for Marinette to be able to speak in your language for absolutely no reason and without getting paid? Nice! Fork the repository. You're looking for [localization.src](src/localization.src). Copy the English locale from here to any text editor, change the **_language** variable from English to the language of your choice and start translating! The rules are the following:

1.  You're prohibited to translate anything in curly brackets caps. For example, you can't translate `{SESSION}`, `{HOST}`, `{SHELLS}`, etc
2.  If you feel your language doesn't have an English terminology counterpart, just transliterate it. Examples of such terminology: "LocalHost", "Service", "Hash", "Crack", etc
3.  Marinette's pronouns are she/her, so if your language has them, translate accordingly
4.  Glued words CAN'T be translated as separate!!! For example, "PublicAddress" can't be translated as "Public Address" in your language

Once you're done, scroll to the bottom of the [localization.src](src/localization.src), make 4 new lines and append your locale after the latest one, commit and open the pull request


### Bug report <a name="contrib-bugreport">

Open up an issue and wait for my response


### Features/Commands/Bug fixes/etc <a name="contrib-code">

If you want to contribute to the code, then look at it first. Still want to contribute? Then you should also know there is absolutely no documentation(lazy me) and you have to guess what and how to change things so they doesn't break! STILL want to contribute? Okie, great! Fork, make source changes, commit, write what exactly you've changed and open the pull request




## Frequently Asked Questions <a name="faq"></a>

**Q: Why on earth would you call a computer program with a human name?**

**A**: Never ask a Woman Her age, a Man, His salary, and Hacktoria - about Their programmes' names

Seriously, though, because everything made with love should be named as a human being


**Q: Why would you create yet another shell when there are already dozens of them?**

**A**: Because all shells lack something that I want and I have wanted something made by myself


**Q: When will you finally update?**

**A**: When I have time and will to do that


**Q: Why the code quality is so bad?**

**A**: I don't know. Maybe because I'm insane and stupid? =D


**Q: Why you left every address unchanged on the screenshots?**

**A**: Because I reset every so often and target has been randomly generated with `raddr` command anyway


**Q: Will you create user manual?**

**A**: Maybe in the future


**Q: Why did you choose MIT-0 as a License?**

**A**: TL;DR: Best for the players' and developers' freedom

I've figured no one cares about license of your application in Grey Hack, so I've decided I want to give users complete freedom over Marinette. You've got her from github? You're free to do whatever you want with her. You've hacked another player and stealen the sources? You're free to do whatever you want. You've got the sources by exploiting a game? Yes, you guessed it, you're still free to do whatever you want. Full source availability also means I'll try my best so that it's leakage doesn't mean a game over for the user


**Q: Why the Reliable way is so tedious?**

**A**: TL;DR: For your own security

As mentioned in the previous question, I want it to be so that the source code leakage doesn't mean full compromise of the user. That's why the password is hashed and all of the future credentials baked in at the compile time will also be encrypted/hashed/etc


**Q: Why the hell you're using custom sorting algorithms?**

**A**: Because built-in sort's impossible to perform with a predicate(Unless I'm missing something. If that's the case, open up a pull request)




## Similar projects <a name="similar-projects"></a>

Another cute shell projects:

-   [5hell](https://github.com/jhook777/5hell-for-Grey-Hack-the-Game) by Plu70. Keep in mind the github updates less frequently than the in-game site, so look for most up-to-date version in the game(As of 31 Jan 2024 the official in-game website is www.5hell.org)
-   [SeaShell](https://github.com/Tuna-Terps/SeaShell-greyhack-game) by Tuna Terps
-   [rocShell](https://github.com/rocketorbit/rocShell) by rocketorbit
-   [Lunar](https://github.com/cloverrfoxx/greyhack) by Clover if you are experienced enough to remove backdoor functionality, [Unclovered Lunarium](https://github.com/h4cktoria/unclovered-lunarium) by myself if you are not
-   [Project Pollux](https://github.com/SidiaDevelopment/greyhack-console) by Sidia
-   [Project p1an0Xshell](https://github.com/wh0wfg/greyscripts-p1an0) by Irtalhmu
-   [Project Vexxed](https://github.com/WizeWizard42/GreyHack-Vexxed) by WizeWizard
-   [OpenViper](https://github.com/cantemizyurek/viper-3.0) by SkidMall
-   [MTX Framework](https://github.com/tuonux/mtx) by tuonux. Not a shell, just an interesting project that I've decided to include anyway

If you want me to add your shell, then open an issue and I'll add you as fast as I can! The exception is proprietary software




## License <a name="license"></a>

Marinette is licensed under MIT No Attribution. See [here](LICENSE) for full details

[Simple Text Editor](https://github.com/rocketorbit/Simple-Text-Editor-for-Grey-Hack) is licensed under MIT License. See [here](LICENSE-Simple-Text-Editor-for-Grey-Hack) for full details




## Thanks and Credits <a name="thanks-and-credits"></a>

Special thanks and credits goes to:

-   [Kurouzu](https://steamcommunity.com/profiles/76561198135838638) - for [Grey Hack](https://store.steampowered.com/app/605230/Grey_Hack/)
-   [Joe Strout](https://github.com/JoeStrout) - for [MiniScript](https://github.com/JoeStrout/miniscript)
-   [Clover](https://github.com/cloverrfoxx) - for [Lunar](https://github.com/cloverrfoxx/greyhack), from where I've taken and adapted a lot of design choices
-   [Roupi](https://www.greyrepo.xyz/users/roupi) - for [Scan class module](https://www.greyrepo.xyz/posts/scan-class)
-   [Finko42](https://github.com/Finko42) - for [Encryption and Hashing algorithms](https://github.com/Finko42/GreyHack)
-   Ariavne - for allowing me to use their nickname as a command name(see `ariadne`)
-   [rocketorbit](https://github.com/rocketorbit) - for [Simple Text Editor](https://github.com/rocketorbit/Simple-Text-Editor-for-Grey-Hack)
-   Guest - for Ukrainian translation
-   Simonize - for color scheme(see `NoAuthV3Ocean` theme) and Polish translation

If I've somehow forgotten to mention you in here then accept my apologizes! Open an issue and I'll add you as fast as I can!
