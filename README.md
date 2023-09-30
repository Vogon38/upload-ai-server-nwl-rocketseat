### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or later)
- [pnpm](https://pnpm.io/) (v6 or later)

### Installing

1. Clone the repository:

   ```sh
   git clone https://github.com/Vogon38/upload-ai-server-nwl-rocketseat.git
   ```

2. Install dependencies:

   ```sh
   pnpm install
   ```

### Dependencies

- `fastify`
- `zod`
- `ai`
- `prisma`
- `openai`


### Running the App

1. Start the local database (optional):

   ```sh
   pnpm run dev
   ```

2. Start the Prisma Studio to view the database:

   ```sh
   pnpm prisma studio
   ```

3. Seed the database:

   ```sh
   pnpm prisma db seed
   ```

## API Routes (To view all available routes, click [here](https://github.com/Vogon38/upload-ai-server-nwl-rocketseat/tree/main/src/routes) 🧐)

### `POST /videos/:videoId/transcription`

This route creates a transcription for a given video file using the OpenAI API.

#### Request Body

```json
{
    "prompt": "Transcribe the following video."
}
```

#### Response Body

```json
{
    "transcription": "This is the transcription of the video."
}
```


### `POST /ai/complete`

This route generates an AI completion for a given video prompt.

#### Request Body

```json
{
    "videoId": "123e4567-e89b-12d3-a456-426655440000",
    "prompt": "What is the meaning of life?",
    "temperature": 0.5
}
```

#### Response Body

```json
{
    "id": "cmpl-1234567890",
    "created": 1631234567,
    "model": "gpt-3.5-turbo-16k",
    "choices": [
        {
            "text": "The meaning of life is to be happy.",
            "index": 0,
            "logprobs": null,
            "finish_reason": "stop"
        }
    ]
}
```