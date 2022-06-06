TextMate bundle for whitespace
==============================

So far it has two grammars it injects into all other scopes. It adds the scopes invalid.illegal.whitespace.trailing to all trailing whitespace and invalid.illegal.whitespace.mixed to all occurrences of mixed spaces/tabs. This means you can spot all your whitespace hiccups before Git does. More information [here](http://mads379.github.com/posts/whitespace-tmbundle "here").

**Author**: Mads Hartmann Jensen

Install
-------

If you have git, you can install cloning the repository to your user library folder:

    mkdir -p ~/Library/Application\ Support/Avian/Bundles
	cd ~/Library/Application\ Support/Avian/Bundles
    git clone https://github.com/mads379/Whitespace.tmbundle.git

If you don't have git, you can download it (using the zip button in the bar), extract the zipfile and copy the extracted folder to `~/Library/Application Support/Avian/Bundles`.

# Strip Whitespace On Save

**TextMate 2 bundle:** Strips trailing whitespace from current document when saving. Works nicely with my [Save On Focus Lost bundle][bomberstudios__Save-On-Focus-Lost.tmbundle]. 

- If you need whitespace highlighting, check Mads Hartmann's superb [Whitespace bundle][mads379__Whitespace.tmbundle]. 
- If you happen to need new lines at EOF, then check Mike Szyndel's [Ensure New Line at the EOF bundle][hajder__Ensure-New-Line-at-the-EOF.tmbundle], which is based on mine.

[bomberstudios__Save-On-Focus-Lost.tmbundle]:  https://github.com/bomberstudios/Save-On-Focus-Lost.tmbundle
[mads379__Whitespace.tmbundle]:                https://github.com/mads379/Whitespace.tmbundle
[hajder__Ensure-New-Line-at-the-EOF.tmbundle]: https://github.com/hajder/Ensure-New-Line-at-the-EOF.tmbundle


## Installation

- Clone the git repo to `~/Library/Application\ Support/TextMate/Bundles/Strip-Whitespace-On-Save.tmbundle`
- Relaunch TextMate 2


## Customization

Customizing the bundle is easy.


### Using `.tm_properties`

Suppose you want to avoid stripping white space on some specific files (like CSV and YAML). Just add the following to your `.tm_properties` file:

```ini
[*.csv]
scopeAttributes = attr.keep-whitespace

[*.yml]
scopeAttributes = attr.keep-whitespace
```

If you wanted to preserve whitespace for that messed-up whitespace project of yours, just drop this in its `.tm_properties` file:

```ini
scopeAttributes = attr.keep-whitespace
```

Of course, you can combine those two approaches for complete control over whitespace-stripping!

If you want to know which scope corresponds to each language, just hit <kbd>^⇧P</kbd> (*Show Scope*) on a document of that type, and you'll get a nice tooltip with the scope namespaces that apply at the current cursor's position.


### Without Using `.tm_properties`

If you can't (or don't want to) use `.tm_properties` files, just open the Bundle Editor (**Bundles menu ▶︎ Edit Bundles...** or pressing <kbd>^⌥⌘B</kbd>) and add `-text.tabular.csv` in the command's *Scope Selector* field:

![screenshot 2013-12-05 20 35 46](https://f.cloud.github.com/assets/3832/1686305/20f9cb7e-5de5-11e3-8b76-1c09d9e40137.png)

- **To exclude multiple file types,** just add `(space)-scope.namespace`. 
  For example, to exclude CSV and YAML, write: `-text.tabular.csv -source.yaml`.
- **To work _only_ on specific file types,** use the namespace only, without the minus sign (e.g., to strip only CSV files, write `text.tabular.csv`). 
- **To include multiple file types,** just add them separated by comma (i.e: `text.tabular.csv, source.yaml, text.html.markdown`).


## Notes

**You need to be using at least TextMate version 2.0.0-alpha.9317**. 

To get the most recent nightly build, open **Preferences ▶︎ Software Update** and **<kbd>⌥</kbd>-click the "Check Now"** button . This will grab the latest version, rather than the one you get by just clicking the button.

Enjoy!

# Ensure New Line at the EOF

TextMate 2 bundle: Adds new line at EOL if missing in current document when saving. Inspired by [Strip Whitespace On Save by Ale Muñoz](https://github.com/bomberstudios/Strip-Whitespace-On-Save.tmbundle).

## Installation

- Clone the git repo to  `~/Library/Application Support/Textmate/Bundles`
- Relaunch TextMate 2

## Customization using `.tm_properties`

Customizing the bundle is easy.

Suppose you want to avoid stripping white space on some specific files (like CSV and YAML). Just add the following to your `.tm_properties` file:

```ini
[*.csv]
scopeAttributes = attr.do-not-ensure-new-line-at-the-eof

[*.yml]
scopeAttributes = attr.do-not-ensure-new-line-at-the-eof
```

If you wanted to preserve whitespace for that messed-up whitespace project of yours, just drop this in its `.tm_properties` file:

```ini
scopeAttributes = attr.do-not-ensure-new-line-at-the-eof
```

Of course, you can combine those two approaches for complete control.

If you want to know which scope corresponds to each language, just hit <kbd>^⇧P</kbd> (*Show Scope*) on a document of that type, and you'll get a nice tooltip with the scope namespaces that apply at the current cursor's position.

## Notes

**You need to be using at least TextMate version 2.0.0-alpha.9317**. Open Preferences » Software Update and **ALT-click the "Check Now"** button to get the most recent nightly build (this will grab a latest version than the one you get by just clicking the button).

Enjoy it!
