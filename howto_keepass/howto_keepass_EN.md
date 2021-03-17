# How to - Keepass

- [How to - Keepass](#how-to---keepass)
  - [Introduction to the software](#introduction-to-the-software)
  - [Installation](#installation)
    - [On Windows](#on-windows)
    - [Language package installation](#language-package-installation)
  - [Usage](#usage)
    - [Create a database](#create-a-database)

## Introduction to the software

[KeePass][website] is a software from the "password managers" family. Its purpose is to save in an database file all off your passwords. This database is of course encrypted to guarantee the confidentialy of the information contained within.  
Other password manager softwares exist, but I have not tested them personally ([1Password][1password], [LastPass][lastpass], ...). [KeePass][website] is a good pick for managing your passwords since it's recommanded by the [ANSSI][anssi] (CERT-FR).

## Installation

### On Windows

The software can be downloaded from the official KeePass website, in [Downloads](https://keepass.info/download.html) section. Please make sure you download version 2.x.y, latest available and maintained version.  
The installation process is the same as for any other software.

### Language package installation

The language packages can be found in the [Translations](https://keepass.info/translations.html) section. Choose the language package corresponding to the downloaded and installed KeePass version.  
One the package is downloaded, open the KeePass software, go to "Display > Change Language...". On the bottom left part of the newly opened window, click on "Open Folder". The Windows Explorer opens up in the folder where all language packages are stored. Copy the downloaded language pack there.  
Relaunch KeePass, and re-select "Display > Change Language..." : your language is now available.

## Usage

### Create a database

1. After opening the software, select the icon to create a new database, or use the keyboard shortcut `Ctrl + N`, or select "File > New...". ![Creating the database](1_creer_base.png)
1. On the next screen, select the location for your future new database, as well as its name. ![Saving the database](2_save_base.png)
1. On the next screen, you are asked to type in the master password for your database. This password is going to protect all of your other passwords. It's important that you choose it well. Some tips:
   1. A strong password is mainly defined by its length, not on the richness of the dictionnary used
   1. Introducing some special characters and/or numbers by substituting some regular letters will increase the strength of your password (1337 code)
   1. It's easier to remember a password based on ourselves than an apparently random series of characters
   1. The software estimates the strength of your password in bits. Currently, a password is considered strong if its complexity of over 80 bits.
   1. Some good password examples:
      1. 1REALLYd0n'tlikec00kies!!
      1. Hetalkstomelightly,Is33l1f31np1nk
      1. Cyb3rs3cur1ty1sNOTHARD1fw34llc0ntr1but3...
1. Once your password is chosen and validated, the following screen offers several elements. We will only discuss the tabs of interest, but you're free to explore the other options
   1. "General" tab: type in the name you wish to give to your databse. ![Naming the database](3_onglet_gnrl.png)
   1. "Security" tab: it's the most important one when creating your database. Its robustness depends on the settings chosen here.
      1. Encryption algorithm: chose "AES/Rijndael (256-bits key, FIPS 197)"
      1. Key-derivation function: "AES-KDF"
      1. To define the number of iterations, click the "1 second delay" button at the bottom of the window ![Setting up security](4_onglet_securite.png)

Your new databse is now created and ready to use. Save it right now (`Ctrl + S`)!

[website]: https://keepass.info
[1password]: https://1password.com/
[lastpass]: https://www.lastpass.com/fr
[anssi]: https://www.ssi.gouv.fr/