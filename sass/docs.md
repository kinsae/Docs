## What can we do

1.  Variables

        $color1: red;
        $bgColor: #ddd;

2.  Nest selector

            header {
                ...

                span {
                    ...
                }
            }

    Complied as:

            header span {
                ...
                ...
            }

    More complex:

            header {
                ...

                span {
                    ...

                    &:hover {
                        ...
                    }

                    &::before {
                        ...
                    }
                }
            }

3.  Import scss

            _header.scss
            _footer.scss

    Note: `_` is required before file name

    Import as:

            @import "./header";
            @import "./footer";

    Note: `_` and `.scss` is omited while importing

4.  mixin

    Used to implement common styles.

    Defining mixin:

            @mixin funcName() {
                ... [reusable scss here] ...
            }

            /* can accept parameters */

            @mixin newFunc($color, $padd) {
                backgrpund-color: $color;
                padding: $padd;
                ... [reusable scss here] ...
            }

    Including mixin:

            header {

                @include funcName();

                @include newFunc(red, 12);
            }

5.  Extend styles

            body {
                @extend header;  /* inherits styles from header */
                color: white;    /* overrides style */
            }

            header {
                color: red;
                background-color: green;
            }

6.  Calculation

            + , - , * , / , %


            header {
                padding: 10px + 5px;
                background-color: green;
            }
