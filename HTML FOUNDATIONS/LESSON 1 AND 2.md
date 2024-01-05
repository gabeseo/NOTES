Elements - Elements on an HTML page are pieces of content wrapped in opening and closing HTML Tags

Tags - Opening tags tell the browser this is the start of an HTML element. They are comprised of a keyword enclosed in angle brackets <>

<p>Some text content</p>
    <p> is the opening tag 
    (some text content) represents content wrapped within the opening and closing tags    
    </p> is the closing tag

The opening and closing tags tell the browser what content the element contains. The browser then uses this information to determine how it should interpret and format the content
Some HTML elements do not have a closing tag.
    i.e. <br /> or <img/>, but could be used without the closing forward slash <br> or <img>

We need to let the computer know we are making an HTML file, so we appended the filename with the .html extension
We should always name the HTML file that will contain the homepage of our website index.html because web servers will by default look for an index.html page when users land on our websites

-----------------------------------------------------------

<!DOCTYPE html>
Every HTML page starts with a doctype declaration to tell the browser what version of HTML it should use to render the document. We do this by <!DOCTYPE html>

<html lang="en">
</html>
After declaring the doctype, we need to provide an <html> element as this is what is knows as the root element of the document, meaning every other element in the document will be a descendant from this
The word lang represents an HTML attribute which is associated with the given HTML tag i.e. <html> in this case, which give more information about the HTML elements

What is the lang attribute?
    - lang specifies the language of the text content in the element
    - It is used for improving accessibility of the webpage and allows assistive technologies to adapt according to the language and invoke correct pronunciation

Head element
    - The <head> element is where we put important meta information about our webpages, and stuff required for our webpages to render correctly in the browser
    - Inside the <head>, we should not use any element that displays content on the webpage
        
        Meta Element
            - We should always have the <meta> tag with the charset encoding of the webpage in the <head> element: <meta charset="utf-8">
            - Ensures the webpage will display special symbols and characters from different languages correctly in the browser
        Title Element
            - Another element that should be included in the head of an HTML document is the <title> element: <title>My First Webpage</title>
            - This is used to give webpages a title displayed on the webpage's browser tab
            - Without it, it would defualt to its file name; in this case it would be <index.html>

Body element
    - The body element goes within the <html> element and is always below the <head> element
    
Viewing HTML files in the browser
    - How do you view the HTML boilerplate (index.html) file in the browser?
        1. Drag and drop an HTML file from your text editor into the address bar of your browser
        2. Find the HTML file in your file system and double click
        3. Use the terminal to open the file in your browser
            a. Ubuntu - Navigate to the directory containing the file and type google-chrome index.html
            b. masOS - Navigate to the directory containing the file and type open./index.html
