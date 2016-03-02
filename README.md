# ibus-coptic
Unicode Ibus keyboard input for Sahidic Coptic for Linux systems

## Why a Coptic keyboard?
This is not a font package, but a keyboard.  It can use any unicode font that includes Coptic characters, such as [Noto Sans Coptic](https://www.google.com/get/noto/#sans-copt).

In order to use a Coptic unicode font, you would need to know the associated unicode values for the letters or use a character chooser, and input them one at a time.  This is extraordinarily tedious for scholarly work.  This keyboard instead uses a US English keyboard to insert the Coptic unicode values.  When activated, pressing 'a', inserts ⲁ, 'b' inserts ⲃ, etc.

## What is Sahidic Coptic?
Sahidic is dialect of Coptic found in Upper Egypt and was the language used by early monks.  As such, extant literature includes early translations of the Bible and writings from early church leaders.  The Coptic language family includes more characters than are currently supported by this keyboard, but if there is interest, it can be expanded to support other dialects, though it should otherwise prove useful for Bohairic and Akhmimic.

## Mapping
I've largely followed Greek keyboard paradigms, with some phonetic exceptions.  For instance, 'h' returns ϩ instead of ⲏ.  

## Dependencies
This keyboard is based on generating an ibus table.  Therefore, you will need a system that uses ibus for managing input (ie, most modern Linux distrubitions).  

You will need to install:
* ibus-setup
* ibus-table
* Any font that supports Coptic

Note that your distribution may name these differently.  

## Installation
Assuming that ibus-table installs to /usr/share/ibus-table:

``` bash
$ sudo ibus-table-createdb -n /usr/share/ibus-table/tables/coptic.db -s coptic.txt
$ ibus-daemon -drx
```

You should now be able to find it by searching for "Coptic" in `ibus-setup` or the Gnome language settings.  It might first show up as "Other" but clicking on Other should then give the option to select Coptic.  You should then be able to switch between Coptic and your regular language with a simple keyboard shortcut!
