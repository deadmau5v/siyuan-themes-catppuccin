# Contributing

Contributions are always appreciated, especially if you want to use your contribution as an opportunity to learn more about git, CSS, SiYuan, etc. or expand the theme for a plugin you use. This is an inclusive project, and you can contribute (without judgment!) regardless of skill level. Before contributing, please take a moment to read the below information regarding the theme's structure and color usage (but don't worry about perfection; we can always nail things down in review). If you are unsure how to contribute after reading the section below, open an issue and we can talk through it.

## Theme layout and colors

The theme is written in CSS using SiYuan's CSS variable system. The repository includes a `.stylelintrc.yml` file if you care to use [Stylelint](https://stylelint.io/).

The theme defines Catppuccin colors as CSS variables that can be used throughout the stylesheet. Color usage can be found in the main `theme.css` file.

## What colors go where?

SiYuan has a few selectors to keep in mind when modifying its CSS. Three of the more important ones: `:hover`, `.b3-menu__item--current`, and `.fn__active`.

The full palette aims to use colors in the following ways:

+ Active items (`.fn__active`, `.b3-menu__item--current`)
  + `var(--ctp-mauve)` is used for active files in the file explorer sidebar, the active page in the settings sidebar, and so on
  + `var(--ctp-pink)` is used for active button icons
+ Selected items
  + `var(--ctp-accent)` is used when items in menus are selected, when items in search results are selected, and so on
  + Items in this category will often need their `color` changed from something like `var(--base-color)` to `var(--base-color-on-accent)`
+ Hover states (`:hover`)
  + `var(--ctp-accent)` is used when hovering over the file explorer sidebar, settings sidebar, and most other "UI links"
  + `var(--ctp-pink)` is used when hovering over buttons and other "interactive" UI elements
  + Hovering over an item should cause either some part of it to get brighter or its text to become underlined

When transitioning from a default state to one of the above states, it's good practice to add a transition:

```css
a-guy {
  color: var(--base-color);
  transition: color 0.15s ease-in-out;
}

a-guy:hover {
  color: rgb(var(--ctp-accent));
}
```

## Working with the theme

Here's one way to work with the theme:
+ Fork or clone the repository
+ From your terminal, `cd` to the repository
+ Make your changes to `theme.css` or the source files in `src/`
+ Test the theme in SiYuan by:
  + Copying `theme.css` to your SiYuan themes directory:
    - **Windows**: `%APPDATA%\SiYuan\appearance\themes\Catppuccin\`
    - **macOS**: `~/Library/Application Support/SiYuan/appearance/themes/Catppuan/`
    - **Linux**: `~/.local/share/SiYuan/appearance/themes/Catppuccin/`
  + Refreshing SiYuan or reloading the theme
+ Make liberal use of the developer tools in SiYuan (`Ctrl+Shift+I` or `Cmd+Option+I`)

## CSS for plugins

If you are contributing plugin-related CSS, you can add your styles to the appropriate sections in `theme.css`. Add a comment indicating the name of the plugin you're adding CSS for and write your CSS below the comment.

## Submitting changes

+ Fork the repository
+ Create a new branch for your changes
+ Make your changes and test them thoroughly
+ Commit your changes with a clear commit message
+ Push to your fork and submit a pull request

Thank you for your interest in improving Catppuccin for SiYuan!
