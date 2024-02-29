# ModelflowAI<br/>Ollama

Ollama is a PHP package that provides an easy-to-use client for the ollama API.

## Installation

Use the package manager [composer](https://getcomposer.org/) to install Ollama.

```bash
composer require modelflowai/ollama
```

## Usage

```php
use ModelflowAi\Ollama\Ollama;

// Create a client instance
$client = Ollama::client();

// Use the client
$chat = $client->chat();
$completion = $client->completion();
$embeddings = $client->embeddings();

// Example usage of chat
$chatResponse = $chat->create([
    'model' => 'llama2',
    'messages' => [['role' => 'user', 'content' => 'Hello, world!']],
]);
echo $chatResponse->message->content;

// Example usage of completion
$completionResponse = $completion->create([
    'model' => 'llama2',
    'prompt' => 'Once upon a time',
]);
echo $completionResponse->response;

// Example usage of embeddings
$embeddingsResponse = $embeddings->create(['prompt' => 'Hello, world!']);
echo $embeddingsResponse->embedding;
```

For more examples, see the [examples](examples) directory.

## Testing & Code Quality

To run the tests and all the code quality tools with the following commands:

```bash
composer fix
composer lint
composer test
```

## Open Points

### Model API

The Model API is another area that we are actively working on. Once completed, this will provide users with the ability
to manage and interact with their AI models directly from the Ollama package.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

This package is available under the [MIT license](LICENSE).
