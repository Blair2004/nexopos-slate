

# Authentication

## Generating Token

One of the requirement to get started is to have a running instance of NexoPOS. If you don't know yet how to install NexoPOS, you can refer to this [documentation](https://my.nexopos.com/en/documentation/getting-started/download-and-install). Now, we'll head to your profile (the authenticated user) to generate a token.

<aside class="notice">
The generated token will allow any app using it to behave as the user who generated the token. Some actions might be restricted if the authenticated user doesn't have enough right to perform them.
</aside>

![generate-token](generate-token.png)

The generated token will appear on a popup. Note that the token will only be displayed once. If that token is lost, you'll need to generate a new one.

![token-generated](token-generated.png)

We'll now use this token on our header like this.

`Authorization: Bearer [token]`

## Testing Token

> Testing Token

```php
# With Laravel Http Client
use Illuminate\Support\Facades\Http;

$client   = Http::withToken( '[yourtoken]' )->acceptJson()->get( '/api/user' );

```

```js
// using Axios with Javascript.
const axios = require('axios');
const API_URL = 'https://example.com/api/user';
const TOKEN = 'your_jwt_token_here'; // Replace with your actual JWT token

async function authenticate() {
    try {
        const response = await axios.get(API_URL, {
            headers: {
                'Authorization': `Bearer ${TOKEN}`,
                'Content-Type': 'application/json'
            }
        });

        console.log('Response:', response.data);
    } catch (error) {
        console.error('Error:', error.response ? error.response.data : error.message);
    }
}

authenticate();
```

NexoPOS token doesn't expires until they are manually revoked by the user. This behavior is likely to change in the future, therefore you should implement mecanism for testing authentication token.