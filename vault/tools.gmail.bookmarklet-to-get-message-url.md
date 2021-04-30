---
id: ce06d23b-c057-4247-83c8-05ca859c9611
title: Bookmarklet to Get Message URL
desc: ''
updated: 1619309205139
created: 1619308442668
---

Here is a bookmarklet that you invoke via Bookmarks in Chrome.

It gets the URL of the message (could be the entire thread) for the currently showing GMail message, if GMail is actve in the current tab

To use (Chrome on ACER so far):

1. open GMail to the message you want the URL for
2. click "More ..." vertical 3 dots UR corner
   > Bookmarks > GMAil URL Getter
3. Paste (CTRL-V) the captured URL into whatever (DYNA, Obsidian, Dendron)

Here is the pertinent part

>

# Obtain a link to a specific email in GMail - Stack Overflow

> ## Excerpt
>
> How can I obtain a link (a URL) to a specific email in GMail? I want to click that link and open the specific email.

---

If you are happy with a [bookmarklet](https://en.wikipedia.org/wiki/Bookmarklet), you can try adding this to your bookmarks:

```
javascript:(function()%7Basync%20function%20copyPermalink()%20%7Btry%20%7BsearchURL%20%3D%20'https%3A%2F%2Fmail.google.com%2Fmail%2Fu%2F0%2F%23search%2Fmsgid%253A'%3BmessageId%20%3D%20document.querySelector('div%5Bdata-message-id%5D').getAttribute('data-message-id').substring(7)%3Bawait%20navigator.clipboard.writeText(searchURL%20%2B%20messageId)%3Bconsole.log('Mail%20message%20permalink%20copied%20to%20clipboard')%3B%7D%20catch%20(err)%20%7Bconsole.error('Failed%20to%20copy%3A%20'%2C%20err)%3B%7D%7DcopyPermalink()%7D)()
```

It essentially searches the currently focussed email for its `data-message-id` attribute, and then converts that into a search url using the `msgid` predicate (this doesn't seem to be documented, but was quite guessable.)

Caveat: Seems to work with or without a preview pane, but this hasn't been extensively tested.

[Short permalink to this answer](https://stackoverflow.com/a/66327289)

](https://stackoverflow.com/users/13547445/james-gollan)
