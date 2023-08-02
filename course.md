# Building Your First Open AI Plugin

https://github.com/openai-php/client

---

## Course Overview
This course is designed to guide you through the process of creating your first OpenAI plugin. The purpose of the course is to provide a practical, hands-on learning experience that will help you understand how to interact with APIs, specifically the OpenAI API, and how to integrate this functionality into a web plugin.

---

The course is motivated by your desire to automate your task management and your interest in exploring the capabilities of AI and machine learning. By creating a simple OpenAI plugin, you'll gain a better understanding of how AI can be used in practical applications, and you'll develop skills that will be invaluable in your future projects.

---

## Requirements
This course assumes that you have a solid understanding of PHP and experience with Docker and Lando. You should be comfortable setting up your own development environment and writing basic PHP code. You should also have a basic understanding of JSON and APIs.

--- 

## Assumed Knowledge
The course assumes knowledge of PHP, Docker, and Lando for setting up the development environment. Familiarity with JSON and APIs is also assumed, as the course involves interacting with the OpenAI API.

---

## Course Structure:

---

### Module 1: Introduction to OpenAI and ChatGPT

#### Lesson 1.1: What is OpenAI and ChatGPT?

---

 In this lesson, we'll explore the origins and purpose of OpenAI, a research organization focused on ensuring artificial general intelligence (AGI) benefits all of humanity. We'll also introduce ChatGPT, a large-scale language model developed by OpenAI that can generate human-like text based on the input it receives.

---

OpenAI is an artificial intelligence research lab made up of both for-profit and non-profit arms. OpenAI's mission is to ensure that artificial general intelligence (AGI) benefits all of humanity. They aim to build safe and beneficial AGI directly, but they're also committed to aiding others in achieving this outcome.

---
ChatGPT, on the other hand, is a product of OpenAI. It's a language model that uses machine learning to produce human-like text. It's trained on a diverse range of internet text, but it doesn't know specifics about which documents were in its training set or any personal data unless explicitly provided in the conversation.

---
#### Lesson 1.2: Understanding the capabilities of ChatGPT

This lesson will delve into the capabilities and potential applications of ChatGPT. We'll discuss how it can be used to generate creative writing, draft emails, write code, answer questions, tutor in a variety of subjects, translate languages, simulate characters for video games, and much more.

---

ChatGPT is a versatile tool with a wide range of applications. It can generate creative writing, draft emails or other pieces of text, write code, answer questions, provide tutoring in a variety of subjects, translate languages, and even simulate characters for video games. However, it's important to remember that while ChatGPT can generate very human-like responses, it doesn't understand the text in the way humans do and isn't conscious.

---

ChatGPT is a versatile tool with a wide range of applications. It can generate creative writing, draft emails or other pieces of text, write code, answer questions, provide tutoring in a variety of subjects, translate languages, and even simulate characters for video games. However, it's important to remember that while ChatGPT can generate very human-like responses, it doesn't understand the text in the way humans do and isn't conscious.

---

Here's a simple diagram to illustrate the capabilities of ChatGPT:

---

### Module 2: Getting Started with the OpenAI API

---
#### Lesson 2.1: Setting up your OpenAI account

In this lesson, we'll walk you through the process of setting up your OpenAI account. This includes signing up on the OpenAI website, accepting the terms of service, and understanding the account dashboard.

---

To set up your OpenAI account, you'll need to visit the OpenAI website and sign up. During the sign-up process, you'll be asked to provide some basic information and accept the terms of service. Once you've completed the sign-up process, you'll have access to your account dashboard, which provides an overview of your account activity and settings.

---

#### Lesson 2.2: Understanding API keys

This lesson will introduce you to API keys, which are used to authenticate your requests to the OpenAI API. We'll explain what API keys are, why they're important, and how to manage them securely.

---

API keys are a method of authentication used by many APIs, including the OpenAI API. When you send a request to the API, you'll include your API key in the request to verify your identity. It's important to keep your API keys secure to prevent unauthorized access to your account.

---

API keys are a crucial part of interacting with APIs. They are used to identify the calling program, its developer, or its user to the API. Essentially, an API key is a password that's passed in by the application calling an API. It's a way for the API to ensure that it's interacting with the correct, authenticated user.

---

##### Here are some key points about API keys:

1. **Generation**: When you sign up for an account with OpenAI, you'll be given an API key. This key is unique to your account.

---

2. **Usage**: You'll need to include this API key in the header of every request you make to the OpenAI API. This is how the API knows that the request is coming from you.

---

3. **Security**: API keys are sensitive. They should be kept secure and not shared or exposed publicly. If someone else gets access to your API key, they could potentially use it to make requests on your behalf, which could lead to misuse or abuse.

---

4. **Regeneration**: If your API key is compromised, you should regenerate it immediately. Regenerating an API key will invalidate the old key and issue a new one.

---

5. **Rate Limiting**: API keys are also used for rate limiting. Each OpenAI account has a certain number of requests it can make to the API per minute. The API uses the key to keep track of how many requests you're making.
Understanding API keys and how to use them securely is a crucial part of working with APIs. It's important to manage your keys carefully to ensure the security of your applications.

---

#### Lesson 2.3: Making your first API request

Now that you have your OpenAI account and API key, it's time to make your first API request! We'll guide you through the process of sending a request to the OpenAI API, including how to include your API key in the request.

---

Now that you have your OpenAI account set up and you understand what API keys are, it's time to make your first API request. 

---

When making a request to the OpenAI API, you'll need to include your API key in the request header. This is how the API verifies your identity and ensures you have permission to access the data or functionality you're requesting. 

---
Here's a simple example of how to make a request to the OpenAI API using PHP:

```php
<?php
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api.openai.com/v1/engines/davinci-codex/completions',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS =>'{
    "prompt": "Translate the following English text to French: \'Hello, world!\'",
    "max_tokens": 60
  }',
  CURLOPT_HTTPHEADER => array(
    'Content-Type: application/json',
    'Authorization: Bearer YOUR_OPENAI_API_KEY'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
?>
```

In this example, replace 'YOUR_OPENAI_API_KEY' with your actual OpenAI API key. The 'prompt' field in the POST data is where you specify the task for the model. In this case, we're asking it to translate English text to French.

---

#### Lesson 2.4: Handling API responses

After sending a request to the API, you'll receive a response from the server. This lesson will explain how to interpret these responses and handle any potential errors.

---

After you send a request to the API, you'll receive a response. This response will contain the data you requested, or an error message if something went wrong. In the PHP example above, the response is stored in the `$response` variable and then echoed out.

---

Absolutely, let's dive into Lesson 2.4: Handling API responses.

---

Once you've sent a request to the OpenAI API, the server will process your request and send back a response. This response will contain the information you requested, or an error message if something went wrong.

---

Here are some key points about handling API responses:

1. **Status Codes**: The response from the API will include a status code. This code tells you whether the request was successful or not. Common status codes include 200 (OK), 400 (Bad Request), and 500 (Internal Server Error).

2. **Response Body**: The body of the response will contain the data you requested. In the case of the OpenAI API, this will typically be a JSON object containing the output from the model you interacted with.

3. **Error Handling**: If the status code indicates an error, the response body will usually contain an error message explaining what went wrong. It's important to check the status code and handle errors appropriately in your code.

4. **Parsing the Response**: Since the response body is typically in JSON format, you'll need to parse it to extract the data you need. In PHP, you can use the `json_decode()` function to convert a JSON string into a PHP variable.

---

Here's an example of how you might handle a response in PHP:

```php
$response = curl_exec($curl);

if (!$response) {
    die('Error: "' . curl_error($curl) . '" - Code: ' . curl_errno($curl));
}

$http_status = curl_getinfo($curl, CURLINFO_HTTP_CODE);
curl_close($curl);

if ($http_status != 200) {
    echo "Unexpected HTTP status: " . $http_status . "\n";
    var_dump($response);
} else {
    $data = json_decode($response);
    echo "The model's response: " . $data->choices[0]->text . "\n";
}
```
---

In this example, we first check if the `curl_exec()` function returned a response. If not, we output the error message. Then we check the HTTP status code. If it's not 200 (OK), we output the status code and the response body. If it is 200, we parse the JSON response and output the text generated by the model.

---

### Module 3: Building a Basic "Hello World" Plugin

---
#### Lesson 3.1: Planning your plugin

Before you start coding, it's important to plan out what your plugin will do. In this lesson, we'll discuss how to define the functionality of your plugin and plan out its structure. For this course, we're building a simple plugin that takes user input, sends it to the OpenAI API, and displays the response.

---

Sure, let's delve deeper into the two plugins we're planning to build:

---

a) **Hello World Plugin**
The Hello World plugin is a simple plugin that interacts with the OpenAI API. Its purpose is to provide a basic introduction to using the API and to serve as a foundation for more complex plugins.

---

**Functionality**: The plugin will take a user's input, send it to the OpenAI API, and display the model's response. The user input will be a string of text that serves as a prompt for the AI model.

---

**User Interface**: The user interface will be simple and intuitive. It will consist of a text input field for the user's prompt, a submit button to send the prompt to the API, and a display area for the model's response.

---
**Code Structure**: The plugin will be structured into three main parts: the user interface, the function that sends the request to the API, and the function that handles the API response.

---

#### Lesson 3.2: Setting up your development environment

In this lesson, we'll guide you through the process of setting up your development environment. This includes installing necessary software and setting up a local server for testing your plugin.

---

To develop your plugin, you'll need a suitable development environment. This includes a text editor for writing code (such as Visual Studio Code or Sublime Text), a local server for testing your plugin (such as XAMPP or MAMP), and a web browser for viewing your plugin.

---

Here are the steps you'll need to follow:

---

1. **Choose a Text Editor**: You'll need a text editor to write your code. There are many options available, but some popular choices include Visual Studio Code, Sublime Text, and Atom. Choose one that you're comfortable with.

---

2. **Set Up a Local Server**: To test your plugin, you'll need to set up a local server. This can be done using software like XAMPP or MAMP, which allow you to run a server on your own computer.

---

3. **Install PHP**: Since your plugin will be written in PHP, you'll need to have PHP installed on your computer. You can download PHP from the official website.

---

4. **Install Docker and Lando**: Docker and Lando are tools that help you manage your development environment. They allow you to define your environment in code, making it easy to share and replicate.

---

5. **Get an OpenAI API Key**: To interact with the OpenAI API, you'll need an API key. You can get this from the OpenAI website after you've created an account.

---

6. **Familiarize Yourself with JSON and APIs**: If you're not already familiar with JSON and APIs, now is a good time to brush up on these topics. There are many resources available online to help you learn.

---

Once your development environment is set up, you'll be ready to start coding your plugin!

---

#### Lesson 3.3: Coding your plugin: Sending user input to the API

Now it's time to start coding! In this lesson, we'll show you how to write the code that will take user input, send it to the OpenAI API, and receive a response.

---

1. **Create a Form for User Input**: You'll need to create an HTML form where users can enter their input. This form should include a text input field and a submit button. Here's a simple example:

```html
<form id="user-input-form">
  <input type="text" id="user-input" placeholder="Enter your text here">
  <button type="submit">Submit</button>
</form>
```

---

2. **Handle Form Submission**: You'll need to use JavaScript to capture the user's input when the form is submitted and prevent the page from refreshing. Here's how you might do that:

```javascript
document.getElementById('user-input-form').addEventListener('submit', function(event) {
  event.preventDefault();
  var userInput = document.getElementById('user-input').value;
  sendToAPI(userInput);
});
```

In this code, `sendToAPI` is a function that you'll define in the next step.

---

3. **Send a Request to the OpenAI API**: Once you have the user's input, you can send a request to the OpenAI API. You'll need to use PHP for this step. Here's a basic example of how you might send the request using PHP's built-in `file_get_contents` function:

```php
function sendToAPI($userInput) {
  $url = 'https://api.openai.com/v1/engines/davinci-codex/completions';
  $options = [
    'http' => [
      'method' => 'POST',
      'header' => [
        'Content-Type: application/json',
        'Authorization: Bearer YOUR_OPENAI_API_KEY'
      ],
      'content' => json_encode([
        'prompt' => $userInput,
        'max_tokens' => 60
      ])
    ]
  ];
  $context = stream_context_create($options);
  $result = file_get_contents($url, false, $context);
  return $result;
}
```

In this code, replace `'YOUR_OPENAI_API_KEY'` with your actual OpenAI API key.

---

4. **Handle the API Response**: After you send the request, the API will send back a response. You'll need to write code to handle this response, which we'll cover in the next lesson.

---

Remember, when working with APIs, it's important to handle potential errors. For example, the API might respond with an error if you send an invalid request, or it might not respond at all if there's a problem with the server. Your code should be able to handle these situations gracefully.

---

Once your plugin has received a response from the API, you'll need to display this response to the user. In the next lesson, we'll discuss how to handle the API response and display it in a user-friendly way.

---

#### Lesson 3.4: Coding your plugin: Displaying the API response

In this lesson, we'll guide you through the process of handling and displaying the API response in your plugin. Once you've sent a request to the OpenAI API and received a response, you'll need to parse that response and display the result to the user.

---

Here are the steps you'll need to follow:

---

1. **Parse the API Response**: The OpenAI API sends responses in JSON format, so you'll need to parse the response to extract the data you need. In PHP, you can use the `json_decode` function to parse a JSON response.

---

2. **Extract the Relevant Data**: Once you've parsed the response, you can extract the relevant data. For the "Hello World" plugin, you'll want to extract the translated text.

---

3. **Display the Result to the User**: Finally, you'll need to display the result to the user. You can do this by inserting the result into the HTML of your webpage using JavaScript.

---

Here's a basic example of how you might handle and display the API response:

```php
function handleResponse($response) {
  $data = json_decode($response, true);
  $translatedText = $data['choices'][0]['text'];
  return $translatedText;
}

$apiResponse = sendToAPI($userInput);
$translatedText = handleResponse($apiResponse);

echo "<p>Translated text: $translatedText</p>";
```

---

In this code, `sendToAPI` is the function you defined in the previous lesson to send a request to the API, and `handleResponse` is a new function that parses the API response and extracts the translated text.

---

Remember, when working with APIs, it's important to handle potential errors. For example, the API might respond with an error if you send an invalid request, or it might not respond at all if there's a problem with the server. Your code should be able to handle these situations gracefully.

---
#### Lesson 3.5: Testing your plugin

After your plugin is coded, it's important to test it to make sure it works as expected. In this lesson, we'll guide you through the process of testing your plugin and troubleshooting any issues that arise.

---

For your "Hello World" plugin, manual testing could involve the following steps:

---

1. **Load the Plugin**: Start by loading your plugin in a web browser. Ensure that the form for user input is displayed correctly.

---

2. **Test User Input**: Enter some text into the form and submit it. The text you enter should be "Hello World!" as that's the input your plugin is designed to handle.

---

3. **Check API Interaction**: After submitting the form, your plugin should send a request to the OpenAI API. You won't be able to see this happening, but you'll see the result when the API sends back a response.

---

4. **Check the Displayed Response**: The plugin should display the API's response on the webpage. In this case, you should see the French translation of "Hello World!".

---

5. **Test Different Scenarios**: Try entering different inputs into the form. For example, what happens if you submit the form without entering any text? Your plugin should be able to handle these edge cases gracefully.

---

6. **Check Error Handling**: If possible, check how your plugin handles errors. For example, you could temporarily disable your internet connection to simulate a network error and see how your plugin responds.

---

Remember, the goal of manual testing is to catch any bugs or issues that weren't caught during unit and integration testing. It's your chance to make sure the plugin works from a user's perspective.

---

### Module 4: Course Wrap-Up

---

#### Lesson 4.1: Review of what you've learned

In this final module, we'll review what you've learned throughout the course and discuss how you can apply these skills in your future projects.

---

Here's a summary of what we've covered:

1. **Introduction to OpenAI and ChatGPT**: You've learned about OpenAI and its language model, ChatGPT. You've gained an understanding of the capabilities of ChatGPT and how it can be used to automate tasks and create engaging user experiences.

2. **Getting Started with the OpenAI API**: You've set up your OpenAI account, learned about API keys, and made your first API request. You've also learned how to handle API responses and parse JSON data.

3. **Building a Basic "Hello World" Plugin**: You've planned and built a simple OpenAI plugin that sends a "Hello World!" message to the OpenAI API and displays the translated response. You've set up your development environment, written PHP code to interact with the API, and tested your plugin.

---

By completing this course, you've gained a practical understanding of how to interact with APIs and build web plugins. You've also explored the capabilities of AI and machine learning, and you've developed skills that will be invaluable in your future projects.

---

Remember, learning is a continuous process. There's always more to learn and explore, especially in a rapidly evolving field like AI. Don't be afraid to experiment, try new things, and continue expanding your skills.
