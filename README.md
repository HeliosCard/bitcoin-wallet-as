Welcome to HeliosCard Bitcoin Wallet Android Studio wrapper.

Project Setup
------------------

Sync this repo

Sync the HeliosCard\bitcoin-wallet repo. Put both repos beside each other.

In windows, create a batch file "setupLinks.bat" with the contents:

    mklink /J .\bitcoin-wallet-as\app\src\main\java\de .\bitcoin-wallet\wallet\src\de
    mklink /J .\bitcoin-wallet-as\app\src\main\res .\bitcoin-wallet\wallet\res
    mklink /J .\bitcoin-wallet-as\app\src\main\assets .\bitcoin-wallet\wallet\assets
    mklink /H .\bitcoin-wallet-as\app\src\main\AndroidManifest.xml .\bitcoin-wallet\wallet\AndroidManifest.xml
    mklink /J .\bitcoin-wallet-as\integration-android\src\main\java\de .\bitcoin-wallet\integration-android\src\de
    mklink /J .\bitcoin-wallet-as\app\src\main\java\com .\bitcoin-wallet\wallet\src\com

In Linux, the equivalent commands are:

    mkdir ./bitcoin-wallet-as/app/src
    mkdir ./bitcoin-wallet-as/app/src/main
    mkdir ./bitcoin-wallet-as/app/src/main/java
    ln -s ../../../../../bitcoin-wallet/wallet/src/de ./bitcoin-wallet-as/app/src/main/java/de
    ln -s ../../../../bitcoin-wallet/wallet/res ./bitcoin-wallet-as/app/src/main/res
    ln -s ../../../../bitcoin-wallet/wallet/assets ./bitcoin-wallet-as/app/src/main/assets
    ln -s ../../../../bitcoin-wallet/wallet/AndroidManifest.xml ./bitcoin-wallet-as/app/src/main/AndroidManifest.xml
    ln -s ../../../../../bitcoin-wallet/wallet/src/com ./bitcoin-wallet-as/app/src/main/java/com
    mkdir ./bitcoin-wallet-as/integration-android/src/main/java
    ln -s ../../../../../bitcoin-wallet/integration-android/src/de ./bitcoin-wallet-as/integration-android/src/main/java/de

In windows, create a batch file "clearLinks.bat" with contents:

    rmdir .\bitcoin-wallet-as\app\src\main\java\de
    rmdir .\bitcoin-wallet-as\app\src\main\res
    rmdir .\bitcoin-wallet-as\app\src\main\assets
    del .\bitcoin-wallet-as\app\src\main\AndroidManifest.xml
    rmdir .\bitcoin-wallet-as\integration-android\src\main\java\de
    rmdir .\bitcoin-wallet-as\app\src\main\java\com

The final directory structure will be:

    \helioscard\
    \helioscard\setupLinks.bat
    \helioscard\clearLinks.bat
    \helioscard\bitcoin-wallet\
    \helioscard\bitcoin-wallet-as\

Compiling
---------
1. Run \helioscard\setupLinks.bat
2. In Android Studio open project "helioscard\bitcoin-wallet-as"
3. Compile and run!

Modifying Code
--------------
Most source code changes (.java, .xml, etc.) can be made in the bitcoin-wallet-as project within Android Studio but the actual files being modified are contained in the bitcoin-wallet repro and should be checked into the bitcoin-wallet repo. If a new directory structure is added outside of the links created in the setupLinks.bat file new directory links will need to be created.
There should be very little changes to the files within this repo.
