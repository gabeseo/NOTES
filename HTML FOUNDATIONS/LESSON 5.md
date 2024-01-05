Links and Images

Introduction
 - Links allow us to link to other HTML pages on the web (hence called the web)

Lesson Overview
 * How to create links to pages on other websites on the internet.
 * How to create links to other pages on your own websites.
 * The difference between absolute and relative links.
 * How to display an image on a webpage using HTML.

Anchor elements
 - To create a link in HTML, we use an anchor element
 - Anchor element: Wrapping the text or another HTML element we want to be a link with an <a> tag
 - We have to tell the information within the anchor tags where to go by using an HTML attribute
 - An HTML attribute gives additional information to an HTML element and always goes in the element's opening tag
 - Attribute is comprised of two parts: a name, and a value (not all attributes need a value)
 - Add an href (hyperlink reference) attribute to the opening anchor tag
 - By default, any text wrapped with an anchor tag without a href attribute will look like plain text
 - If the href attribute is present, the browser will give the text a blue color and underline it to signify it is a link

Opening links in a new tab
 - By using the target attribute, we can change the default behavior of the browser of opening links in the same tab to opening links in a separate tab
 - href specifies the destination link, target specifies where the linked resource will be opened; if not present, it will take on the _self value which opens the link in the current tab
 - The rel attribute is used to describe the relation between the current tag and the linked document
    - The noopener value prevents the opened link from gaining access to the webpage from which it was opened
    - The noreferrer value prevents the opened link from knowing which webpage or resource has a link
    - Both are used for security reasons
        - The noopener value prevents phishing attacks (tabnapping) and the norefferer value is added to not let the opened link know your webpage is linked to it
 - Most recent versions of browsers automatically provide the security only if target="_blank"

Absolute and relative links
 - Two kinds of links: Links to pages on other websites on the internet (Absolute), and links to pages located on our own websites (Relative)

 Absolute links
  - A typical absolute link will be made up of the following parts: protocol://domain/path
    - An absolute link will always contain the protocol and domain of the destination

 Relative links
  - Relative links do not include the domain name, since it is on the same site; thus assuming the domain name is the same
  - Organization of our website:
    - By creating a new directory called pages, we needed to relocate the href value to include the pages/ directory since that is the new location of the about file relative to the index file
    - If this doesn't work, prepending ./ before the link will prevent such issues
        - You specify to your code that it should start looking for the file/directory relative to the current directory

A metaphor
 - Think of your domain name (town.com) as a town, the directory in which your website is located (/museum) as a museum, and each page on your website as a room in the museum (/museum/movie_room.html and /museum/shops/coffee_shop.html). Relative links like ./shops/coffee_shop.html are directions from the current room (the museum movie room /museum/movie_room.html) to another room (the museum shop). Absolute links, on the other hand, are full directions including the protocol (https), domain name (town.com) and the path from that domain name (/museum/shops/coffee_shop.html): https://town.com/museum/shops/coffee_shop.html.

Images
 - To display an image in HTML, we use the <img> element
 - The <img> element is self-closing (does not need a closing tag)
    - It instead embeds an image into the page using a src attribute which tells the browser where the image file is located

Parent directories
 - We need to go up one level out of the pages directory into its parent directory so we could then access the images directory
 - To go to the parent directory, we need to use two dots in the relative filepath like this:../
    1. We are going to the parent directory of the pages directory which is PRACTICE
    2. Then, from the parent directory, we can go into the imagees directory
    3. Finally, we can access the dog.jpg file

Alt attribute
 - Every image element must have an alt (alternative text) attribute used to describe the image used

Image size attributes
 - We can specify the height and width attributes in image tags that helps the browser layout the page