# Web Layout

HTML Layout
    Traditional websites used HTML for layout
```html    
    <div class="Navbar"><!---menu---></div>
```

HTML 5 Layout
    Semantic Tag : same as div (division of a page) but has the same meaning related to placing and content on the page
    
    HEADER
    NAV         NAVIGATION BAR IE MENU ITEMS
    SECTION
                ARTICLE
                ASIDE
    FOOTER

Assistive technologies pay attention to these tags
    eg. Screen readers
    eg <img alt="" title="" />
        alt displayed on hover and also read out by screen reader

# CSS
```css
    <button class="buttonTypeRound" />

    <style>
    .buttonTypeRound{
        border-radius:5px;
    }
```
1) Flexbox
    Useful for 1D arrangement of items eg navabar or picture gallery
2) Grid
    set varying column widths to fixed/auto/match content etc
    Also same for rows
    Good got laying out responsive and placing elements with minimum fuss. Good for centering items easily within page or gridbox.


Push website to the internet for FREE and CONNECT it via github with AUTOMATIC DEPLOYMENT on change(ie git push)

BUILD LOCAL
    PUSH TO GITHUB
        DEPLOY TO NETLIFY
CHANGE LOCAL
    PUSH TO GITHUB
        AUTOMATIC DEPLOYMENT

1) Create an account with netlify.com
2) go to gatsbyjs.org for the website starter packs

Homework
    a) Rebuild a couple of flexboxes
    note: can set both horizontal and vertical.
    Check phil's repo philanderson888/showcase.index.html for examples

    b) Grid
        checkout 2019-09-html-intro repo from phil
        Build a webpage using grid to lay out the structure
        Put in 3 features which can be interacted with using JS.