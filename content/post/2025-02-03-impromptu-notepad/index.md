---
title: "How to turn any web page into an impromptu notepad"
date: 2025-02-03T23:44:19+11:00
description: document.designMode plus a confirmation prompt just because
image: images/cover.png
tags:
  - software development
  - javascript
  - guide
---

Let's say you're screen-sharing  during a meeting and you want to take some notes. You also want to screen-share said notes with the group to check that what you're writing matches what they have in mind.

You could open VS Code or your favourite text editor. Or you could create a note using an online tool like [GitHub's gists](https://gist.github.com).

Alternatively you can open your browser's console and execute this arbitrary piece of JavaScript:

```js
document.designMode = "on"

window.addEventListener("beforeunload", (event) => {
  if (!window.confirm()) {
    event.preventDefault()
  }
})
```

This code snippet does the following:
- Enables `document.designMode` to make the entire document editable
- Displays a confirmation modal if the user is about to leave the page. This part's optional but I've included it as I'm the kind of person that would accidentally close a tab and lose all their stuff.

Here's what it looks like in action:

{{< video src="images/design-mode-example-1.mp4" >}}

It also works with empty HTML documents:

{{< video src="images/design-mode-example-2.mp4" >}}

If you want to interact with the page again without losing your notes you can disable `document.designMode` by running the following:

```js
document.designMode = "off"
```

## Browser support

Both `document.designMode` and `Window: beforeunload event` are in [Baseline](https://developer.mozilla.org/en-US/docs/Glossary/Baseline/Compatibility) widely available and have been supported by major browsers since 2015.

## Other potential use cases

- Mockup copy changes
- Edit text on a random website for reasons
- Run your browser's spell checker through the current page

## Resources

- [Document: `designMode` property - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode)
- [HTMLElement: `contentEditable` property | MDN](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable) - Like `document.designMode` but scoped to specific elements
- [Window: `beforeunload` event](https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event) - Has some notes about potential caveats when using this event