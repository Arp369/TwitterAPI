# TwitterAPI
This is a simple Twitter bot written in Go that allows you to post and delete tweets using the Twitter API v2. It uses OAuth1 for authentication and handles environment variables for secure API key management.

## Features

- Post tweets to your Twitter account
- Delete tweets using their ID
- Handles API response errors gracefully
- Loads sensitive credentials from a `.env` file

## Prerequisites

- Go (version 1.14 or higher)
- A Twitter Developer account and a Twitter App to get your API keys and tokens

## Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Arp369/TwitterAPI.git
   cd TwitterAPI
   ```

2. **Initialize Go Modules:**

   If you haven't already initialized Go modules in your project directory, run:

   ```bash
   go mod init TwitterAPI
   ```

3. **Install Dependencies:**

   Use the following command to install the required packages:

   ```bash
   go get github.com/dghubble/oauth1
   go get github.com/joho/godotenv
   ```

4. **Create a `.env` file:**

   In the root of your project directory, create a file named `.env` and add your Twitter API credentials:

   ```plaintext
   API_KEY=your_api_key
   API_SECRET_KEY=your_api_secret_key
   ACCESS_TOKEN=your_access_token
   ACCESS_TOKEN_SECRET=your_access_token_secret
   ```

   Replace the placeholder values with your actual Twitter API credentials.

## Usage

You can run the application with the following commands:

### Post a Tweet

To post a tweet, use the `-text` flag followed by your tweet content:

```bash
go run . -text "Your tweet text here"
```

### Delete a Tweet

To delete a tweet, use the `-delete` flag followed by the tweet ID:

```bash
go run . -delete "tweet_id_here"
```

### Example Commands

```bash
# Post a tweet
go run . -text "Hello, world! This is my first tweet from my Go app!"

# Delete a tweet by ID
go run . -delete "1234567890"
```

## Error Handling

The application provides informative messages for common issues, such as:

- Unauthorized access due to incorrect API keys
- Attempting to delete a tweet that does not exist
- Rate limit errors when too many requests are made in a short period