# How to use local storage and the Cache API

In the early days of the web, client-side storage options were pretty limited. We had cookies, which were small text files that could be used to store a little bit of data on the user's device. But cookies had some serious limitations, such as the 4KB size limit and the fact that they were sent with every request to the server, which could slow down page load times. So, web developers had to get creative with how they stored data on the client side.

Then, in the late 2000s, the Web Storage specification was introduced, which provided a more robust client-side storage option in the form of local storage. Local storage allowed web developers to store key-value pairs on the user's device, with no size limit and no need to send the data with every request to the server. This was a game-changer for web development and allowed for the creation of more advanced web applications.

But as web developers, we're never satisfied, we always want more! And so, in the early 2010s, the Cache API was introduced, giving us the ability to store responses to network requests in a browser-specific cache. This was a huge deal for performance optimization, as it allowed us to store frequently accessed resources on the client side, reducing the need for network requests and speeding up page load times.

And let's not forget about IndexedDB, a more powerful and complex client-side storage option that allows for storing large amounts of structured data in a way that can be queried efficiently. It's like a mini-database on the client side, and it's pretty awesome, but I won't be going into that in this article; check out my next article.

Nowadays, with all these different client-side storage options at our disposal, it's like a smorgasbord of data storage deliciousness. It can be tough to choose which one to use, but the good news is that we don't have to pick just one. We can use a combination of local storage, cache storage, and IndexedDB to create web applications that are fast, reliable, and able to handle large amounts of data.

### To use local storage in JavaScript,

You can use the `localStorage` object. Here is an example of how to set and retrieve a value in local storage:

```javascript
// Set a value in local storage
localStorage.setItem("username", "victor Oz");

// Retrieve a value from local storage
var username = localStorage.getItem("username");
console.log(username); // "victor Oz"
```

### To use cache storage in JavaScript,

You can use the `caches` object. Here is an example of how to cache a network request and retrieve the cached response:

```javascript
// Cache a network request
fetch("https://victoroz.com/pretty-boy.jpg")
  .then(response => caches.open("my-image-cache").then(cache => cache.put(event.request, response)));

// Retrieve a cached response
caches.match("https://victoroz.com/pretty-boy.jpg").then(response => {
    if (response) {
        console.log("Response found in cache")
    } else {
        console.log("Response not found in cache")
    }
});
```

It's worth noting that both local storage and cache storage has limitations in terms of the amount of data that can be stored. Local storage typically has a limit of around 5–10 MB, while cache storage is typically limited to around 50 MB. If you need to store a large amount of data, you will likely need to use a different storage mechanism

As a web developer, it's like having the superpower of being able to control the data on the client side, and you know what they say: with great power comes great responsibility... and a whole lot of debugging. But hey, that's all part of the fun, right?