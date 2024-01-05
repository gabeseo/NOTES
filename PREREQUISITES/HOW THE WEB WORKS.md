How the web works

Clients and servers
 - Computers connected to the internet are called clients and servers
    - Clients are the typical web user's internet-connected devices (i.e. computer or phone) and web-accessing software available on those devices (web browsers like chrome) (ALBION ONLINE)
    - Servers are computers that store webpages, sites, or apps. (LEAGUE OF LEGENDS)
        - When a client device need to access a webpage, a copy of the webpage is downloaded from the server onto the client machine to be displayed in the user's web browser

The other parts of the toolbox

IMAGINE A CLIENT AND SERVER IS CONNECTED BY A ROAD

 - Internet connection: Allows you to send and receive data on the web (street between your house and the shop)
 - TCP (Transition Control Protocol)/IP (Internet Protocol): They are both communication protocols that define how data should travel across the internet. These are transport mechanisms that let you place an order, go to the shop, and buy goods (a car or bike)
 - DNS (Domain Name System): This is like an address book for websites. When you type a web address in your browser, the browser looks at the DNS to find the website's IP address before it can retrieve the website. (looking up the address of a shop)
 - HTTP (Hypertext Transfer Protocol): Application protocol that defines a language for clients and servers to speak to each other (order your goods)
 - Component files: A website made up of many different files, which are like different parts of the goods you buy from the shop
    - Code files: Websites are built primarily on HTML, CSS, and JavaScript
    - Assets: A collective name for all the other stuff that makes a website, such as images, music, video, Word documents, and PDFs

So what happens, exactly? (analogy that's like walking into a shop)
 1. The browser goes to the DNS server, and finds the real address of the server that the website lives on
 2. The browser sends an HTTP request message to the server, asking it to send a copy of the website to the client. This message, and all other data sent between the client and the server, is sent across your internet connection using TCP/IP
 3. If the server approves the client's request, the server sends the client a "200 OK" message, which means "You can look at the website! Here it is!", and then starts sending the website's files to the browser as a series of small chunks called data packets
 4. The browser assembles the small chunks into a complete web page and displays it to you

Order in which componenet files are parsed
 - When browsers send requests to servers for HTML files, those HTML files often contain <link> elements referencing CSS stylesheets and <scripts> elements referencing external Javascript scripts
 - It is important to know the order in which those files are parsed by the browser as the browser loads the page:
    - The browser parses the HTML file first, and that leads to the browser recognizing and <link>-element references to external CSS stylesheets and <scripts>-element references to scripts
    - The browser genereates an in-memnory DOM(Document Object Model) tree from the parsed HTML, generates an in-memory CSSOM structure from the parsed CSS, and compiles and executes the parsed JavaScript
    - As the browser builds the DOM tree and applies the styles from the CSSOM tree and executes the JavaScipt

DNS explained
 - The Domain Name System was created because it is not easy to remember IP addresses

Packets explained
 - Data is sent in thousands of small chunks (small packets). They are corrupted easily and it is easier to replace small chunks when this occurs
 - The packets can be routed along different paths, making the exchange faster and allowing many different users to download the same website at the same time