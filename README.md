# Google Cloud Speech + Web Audio API

Speech recognition and synthesis using the Google Cloud Speech APIs integrated with the Web Audio API for microphone input and playback directly in the browser.

For now authorization only works with an API Key, you can create one at https://console.cloud.google.com/apis/credentials. 
**Make sure you restrict it to only Cloud Speech-to-Text and Cloud Text-to-Speech APIs.**

[Demo](https://andrei.codes/cloud-speech/)

## Usage

```
npm install google-cloud-speech-webaudio
```

### Speech Recognition

```javascript
import { GoogleSpeechRecognition } from 'google-cloud-speech-webaudio';

const GOOGLE_API_KEY = '...';

const speechRecognition = new GoogleSpeechRecognition(GOOGLE_API_KEY);

// start recording microphone audio to a buffer.
// on first run it will request microphone permission.
await speechRecognition.startListening();

// stop recording your audio, send the buffer to Google for transcription
const result = await speechRecognition.stopListening();
```

### Speech Synthesis

```javascript
import { GoogleSpeechSynthesis } from 'google-cloud-speech-webaudio';

const GOOGLE_API_KEY = '...';

const speechSynthesis = new GoogleSpeechSynthesis(GOOGLE_API_KEY);

// make the API call and play the produced speech audio buffer
await speechSynthesis.speak('hello world');
```
