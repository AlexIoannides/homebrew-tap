# My Personal Homebrew Tap

For keeping formulae of old software versions that I may want to revert back to!

## Create your Personal Tap

For example, this repo! The repo must be named `homebrew-tap`. This then need to be tapped - e.g.,

```text
brew tap alexioannides/tap
```

## Adding a new Formula to the Tap

Start by extract a formula - e.g.,

```text
brew extract hashicorp/tap/terraform --version 1.9.1 alexioannides/tap
```

That will yield outout along the lines of,

```text
==> Searching repository history
==> Writing formula for terraform at 1.8.0 from revision bca6603 to:
/opt/homebrew/Library/Taps/alexioannides/homebrew-tap/Formula/terraform@1.9.1.rb
```

Commit and push this to your remote repo - e.g.,

```text
cd $(brew --repo alexioannides/tap)
git pull
git add -A && git commit -m "Add teraform@1.8.0"
git push origin main
```

## Installing Formulae

You can now reinstall old version from you tap - e.g.,

```text
brew install alexioannides/tap/terraform@1.8.0
```

## Debugging

If you having trouble extracting formulae from `homebrew/core`, then run,

```text
brew tap homebrew/core --force
```

As explained [here](https://github.com/orgs/Homebrew/discussions/4326#discussioncomment-5318255).
