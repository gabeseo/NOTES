OVERVIEW
 * How to create paragraphs.
 * How to create headings.
 * How to create bold text.
 * How to create italicized text.
 * The relationships between nested elements.
 * How to create HTML comments.

 Paragraphs
    - When a browser encounters new lines in your HTML, it will compress them down to one long line
    - This will create no new paragraph between the space

    <body>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
        incididunt ut labore et dolore magna aliqua.
      
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
        nisi ut aliquip ex ea commodo consequat.
    </body>


    - If we want to create paragraphs in HTML, we use the paragraph element <p>
    - This will create two separate paragraphs

    <body>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>

        <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
    </body>    


Headings
    - Headings are displayed larger and bolder than other text to signify they are headings
    - There are 6 different headings <h1> to <h6>, <h1> being the most important and biggest heading and <h6> being the the smallest heading


    <h1>This is the biggest heading</h1>
    ...
    <h6>This is the smallest heading</h6>


Strong Element
    - <strong> element makes the text bold which semantically marks texts as important


    Boston is <strong>COLD!</strong>


Em (emphasis) element
    - <em> element makes the text italic which sematically places an emphasis on the text


    Boston is <em>COLD!</em>


Nesting and indentation
    - We indent any elements that are within other elements, known as nesting elements
    - They have a parent and child relationship; the nested elements are the children and the element they are nested within is the parent
    - HTML parent elements can have many children, and elements at the same level of nesting are considered to be siblings


HTML Comments
    - HTML comments are not visible to the browser; they allow us to comment on our code so that other developes or our future selves can read them
    - Enclose the comment with <!-- and --> tags


    <h1>I am a heading</h1>
    <!-- I am a comment -->

    <p>I am a paragraph</p>
    <!-- I am a comment -->

    VSCode shortcut for comments: CNTL + /