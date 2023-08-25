Creating a File Encryption App with JavaScript

Security and privacy are hot topics at the moment. This is an opportunity for us to take an introspective look into the way we approach security. It is all a matter of compromise - convenience versus total lock down. Today's tutorial is an attempt to mix a bit of both.

The app we are going to build today is an experiment that will allow people to choose files from their computers and encrypt them client-side with a pass phrase. No server-side code will be necessary, and no information will be transferred between client and server. To make this possible we will use the HTML5 FileReader API, and a JavaScript encryption library - CryptoJS.

Note that the app doesn't encrypt the actual file, but a copy of it, so you won't lose the original. But before we start, here are a few issues and limitations:

Issues and limitations
The 1MB limit

If you play with the demo, you will notice that it doesn't allow you to encrypt files larger than 1mb. I placed the limit, because the HTML5 download attribute, which I use to offer the encrypted file for download, doesn't play well with large amounts of data. Otherwise it would cause the tab to crash in Chrome, and the entire browser to crash when using Firefox. The way around this would be to use the File System API and to write the actual binary data there, but it is supported only in Chrome for now. This is not an issue with the encryption speed (which is quite fast), but with offering the file for download.

What about HTTPS?

When it comes to encrypting data and securing information, people naturally expect the page to be loaded through HTTPS. In this case I believe it is not necessary, as apart from the initial download of the HTML and assets, no data is transferred between you and the server - everything is done client-side with JavaScript. If this bothers you, you can just download the demo and open it directly from your computer.