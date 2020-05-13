# Highlight
Highlight is a tool for highlighting text on any website, based on the [annotator.js](http://annotatorjs.org/) project.

# Usage
Highlight can be used in 2 ways:  
1. Chrome extension
2. Standalone

In both ways, it allows the following actions:
1. Highlight text (using <kbd>ctrl</kbd>+<kbd>left mouse button</kbd>).
2. Copy highlights to clipboard.

The Chrome extension also allows to: 

3. Save highlights.

# :wrench: Installation

## • Chrome extension  
Follow these steps to use Highlight as a Chrome extension:
   1. Download the repository and extract it  
   2. Go to Chrome's Extensions page, change it to Developer Mode  
   3. Click Load Unpacked to load the extracted folder.  
  
## • Standalone  
Use the following html tags:  
```html
<script src="highlight/js/standalone/dit/bundle.js" type="text/javascript"></script>
<link href="highlight/css/sidebar.css" rel="stylesheet" />
<link href="highlight/css/highlight.css" rel="stylesheet" />
```

# :rocket: Components
Highlight is comprised of 2 components: 

## 1. Highlighting 
Highlighting is done with a simple <kbd>ctrl</kbd>+<kbd>left mouse button</kbd> click.

## 2. Sidebar
### Cards
Any highlighted text is loaded into the sidebar into a designated card. You can interact with cards in the following ways:  
* Erase a card using the trash button. This will also, of course, remove the highlight itself. 
* Swap cards positions by dragging them.
* Click a card to automatically navigate into its respective highlight.
### Buttons
The following buttons are available:  
* **Copy**  
Copies the highlighted text into your clipboard 
* **Save** (currently supported only on the Chrome extension)   
Saves the highlights into Chrome storage, so that when you reload the page your saved highlights will reload .
* **Change position**  
Changes the sidebar position to the right or left side of the screen.

# :pencil: Implementation
## 1. Highlighting
The highlighting functionality is based on [annotator.js](http://annotatorjs.org/) implementation. Specifically, it uses functions from annotator.js's `highlighter.js` file, and its `xpath-range` module.
## 2. Sidebar
The sidebar is built using a [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM). Using a shadow DOM enables the sidebar to load any css file without affecting the original DOM style. 
  * Note: this is why the `.higlight` class lives in its own css file, as it needs to be applied on the DOM itself.

# :hammer: Compilation
In case you're making changes to the javascript code, you'd need to compile using [Webpack](https://webpack.js.org/guides/installation/):
1. `cd` into `js/standalone`.
2. Run:  
  `webpack index.js` 

# :link: Similar Projects
- [hypothesis.io](https://github.com/hypothesis/h)
- [web-highlighter](https://github.com/alienzhou/web-highlighter)
