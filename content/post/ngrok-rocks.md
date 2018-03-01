---
title: "ngrok Rocks!"
date: 2018-03-01T13:44:17+02:00
draft: false
description: Public URL for your localhost server
tags: [public-url, localhost, ngrok, local-webserver]
keywords: [public url, localhost, ngrok, local web server]
---
Earlier this week we had an inner hackathon here at [BigPanda](https://bigpanda.io/).     
At some point, my team needed a way to expose our local web server and build webhook integrations.

I've heard about [ngrok](https://ngrok.com/) before and this seemed like a good opportunity to give it a try.

> Disclaimer: this is **not** a deep dive, only a basic intro not covering the advanced and paid features.

#### Installation
1. Download the binary from [here](https://ngrok.com/download)
2. unzip it      
```
$ unzip /path/to/ngrok.zip
```

Bonus tip - move the executable to a folder in your `$PATH`

#### Usage
Say we’re running our local web server on port `8787`. 

Typing: 
```
$ ./ngrok http 8787
```
will result in ngrok listening on port `8787` and creates the secure tunnel.

![ngrok listens to port 8787](/images/ngrok.png)

Just use one of the two sets of publicly available URLs that map to your local web server

`Forwarding http://86ddc8c6.ngrok.io -> localhost:8787`    
`Forwarding https://86ddc8c6.ngrok.io -> localhost:8787`

If this isn't awesome enough, ngrok also has a dashboard!     
Go to http://127.0.0.1:4040 where you can:

1. Look at your tunnel status - requests coming in and responses from your web server
2. replay requests, especially useful for debugging

#### Bonus

Secure your tunnels:
```
$ ngrok http -auth "user:password" 8787
```

`ngrok` has lots more cool features like using custom subdomains and auto-launching from a configurations file.

It really rocks \m/

![rocks!](https://media.giphy.com/media/dM2xuxnJCg4H6/giphy.gif)

Read more in the official [docs](https://ngrok.com/docs)
