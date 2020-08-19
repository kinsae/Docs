# TABLE OF CONTENTS

## CSS

- ### CSS Anatomy

- ### Selectors

  - Element, Class, ID

  - Combined Selector

  - Pseudo-Class Selector

  - Pseudo-Element Selector

- ### Style Placement

  - Inline Style
  - `<style>...</style>` tag
  - External link

- ### Style Conflict Resolution

  - Origin (Last one to be declared gets the priority)
  - Inheritance (style inherited from parent elements)
  - Merge (non-conflicting styles get merged)
  - Specificity (higher the specificity, higher the priority)

- ### Box Model

  - Margin, Border, Padding, Content
  - Box-sizing
  - Cumulative (right-left) and Collapsing (bottom-top) Margin

- ### Position Elements

  - Float <i>(takes elements out of the regular document flow)</i>
  - Static Position <i>(Default - document flow, except html tag)</i>
  - Relative Position

    <i>(Relative to own normal position; keeps in document flow)</i>

  - Absolute Position

    <i>(Relative to nearest `non-static` parent element; move out of document flow)</i>

  - Fixed Position <i>(Relative to browser window)</i>
  - Sticky Position

    <i>(Based on user scroll. Change between Relative-to-Fixed. Used in nav header)</i>

- ### CSS Properties

  - background, display, border, font, alignment and more

- ### Responsive Design

  - Media Queries: width, height, print, orientation, screen
  - 12-COLUMN GRID LAYOUT
  - `viewport` meta tag

    <i>(turn off mobile zoom). Tells the browser to consider the width of the device as the real width of the screen and set its zoom level to 1, i.e., 100%, so it's not zoomed in or zoomed out.</i>

- ### CSS Frameworks

  - Component vs Utility Frameworks

    <i>Component: full styled components or elements</i><br>
    <i>Utility: css attributes only</i>

  - Bootstrap (Component)
  - Tailwind (Utility)
