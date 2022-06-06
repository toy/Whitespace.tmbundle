# TextMate bundle for whitespace

Combines [Whitespace.tmbundle](https://github.com/mads-hartmann/Whitespace.tmbundle) with  [Strip-Whitespace-On-Save.tmbundle](https://github.com/bomberstudios/Strip-Whitespace-On-Save.tmbundle) and [Ensure-New-Line-at-the-EOF.tmbundle](https://github.com/mszyndel/Ensure-New-Line-at-the-EOF.tmbundle).

Adds two grammars that are injected into all other scopes: `invalid.illegal.whitespace.trailing` to all trailing whitespace and `invalid.illegal.whitespace.mixed` to all occurrences of mixed spaces/tabs. This means you can spot all your whitespace hiccups before Git does.

Also strips trailing whitespace and ensures one newline at EOF in current document when saving.

## Install

```shell
mkdir -p ~/Library/'Application Support'/TextMate/Bundles
cd ~/Library/'Application Support'/TextMate/Bundles
git clone https://github.com/toy/Whitespace.tmbundle.git
```

### Using `.tm_properties` or `~/.tm_properties`

If you want to avoid stripping white space and/or adding newline at EOF on some specific files (like CSV and YAML), add the following to your `.tm_properties` or `~/.tm_properties` file:

```ini
[*.csv]
scopeAttributes = attr.do-not-strip-whitspace

[*.yml]
scopeAttributes = attr.do-not-ensure-new-line-at-the-eof

[*.txt]
scopeAttributes = "attr.do-not-strip-whitspace attr.do-not-ensure-new-line-at-the-eof"
```

Same for complete project:

```ini
scopeAttributes = attr.do-not-strip-whitspace
```

If you want to know which scope corresponds to each language, just hit <kbd>^⇧P</kbd> (*Show Scope*) on a document of that type, and you'll get a nice tooltip with the scope namespaces that apply at the current cursor's position.
