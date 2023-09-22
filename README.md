# InfinityScroll Class

The `InfinityScroll` class is a JavaScript utility for implementing infinite scrolling behavior on a web page. Infinite scrolling is a popular user experience pattern where additional content is dynamically loaded as the user scrolls down a page.

## Features

- Automatically loads more content when a specified target element becomes visible in the viewport.
- Makes AJAX requests to a specified URL to fetch additional data.
- Generates and inserts HTML elements based on the data received from the server.
- Allows for customization of the callback function to handle data rendering.
- Supports the configuration of the number of items to load in each request.

## Getting Started

To use the `InfinityScroll` class in your web application, follow these steps:

1. Include the jQuery library in your project if it's not already included.

2. Create an HTML element at the end of the list you want to scroll. It can include inside some loading element, gif, etc that will be hidded when it is not fetching data.
   
   ```html
   <div id="target_element">
      <img src="loading.gif" />
   </div> 
   ```
3. Include the `InfinityScroll` class in your JavaScript file.

4. Create an instance of the `InfinityScroll` class by passing the required parameters:
   - `target_element`: The ID of the HTML element that triggers infinite scrolling.
   - `url`: The URL for making AJAX requests to load more data.
   - `callback`: A callback function to generate HTML elements from the server response.
   - `amount`: The number of items to load in each request.
   - `post_data` (optional): Additional data to send in the POST request.

5. Customize the `callback` function to generate HTML elements based on your data structure.

6. Enjoy seamless infinite scrolling on your web page!

## Example

```javascript
// Create an instance of the InfinityScroll class
const infiniteScroll = new InfinityScroll(
    'target-element-id',
    'server-api-url',
    (data) => {
        // Custom callback function to generate HTML elements
        // based on the data received from the server.
        return `<div>${data.someProperty}</div>`;
    },
    10, // Load 10 items at a time
    { username: "username"} // additional data for the request
);

// The class will automatically start observing the target element for scrolling.
```
## License
This project is licensed under the MIT License - see the [MIT License](LICENSE.md). file for details.

## Acknowledgments
This class is inspired by the concept of infinite scrolling and uses the Intersection Observer API for efficient scrolling detection.
It utilizes jQuery for making AJAX requests and manipulating the DOM.
Feel free to use and modify this class in your projects. If you encounter any issues or have suggestions for improvements, please [Create an issue](https://github.com/MkFdez/infinity-scroll/issues/new).

Happy scrolling!
