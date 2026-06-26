# TTS Latency Horse-Race

Measures **Time to First Audio Byte (TTFAB)** across five TTS providers: Neuphonic, Gradium, ElevenLabs, Cartesia, and OpenAI.

Results are most meaningful from a European server. The benchmark is set up to use the Europe West Codespaces region by default since that is where Neuphonic's fastest infrastructure is based.

---

## How to Run

### Step 1 - Launch the Codespace

Click the green **Code** button, go to the **Codespaces** tab and click **New with options**. The region should already be set to **Europe West**. If not, set it before clicking Create.

Dependencies install automatically once the Codespace starts.

### Step 2 - Add your API keys

Copy `.env.example` to `.env`:

```bash
cp .env.example .env
```

Open `.env` and fill in your five API keys:

```
OPENAI_API_KEY=...
GRADIUM_API_KEY=...
CARTESIA_API_KEY=...
NEUPHONIC_API_KEY=...
ELEVENLABS_API_KEY=...
```

### Step 3 - Run the notebook

Open `latency_horserace.ipynb` and click **Run All**. The final cell prints the mean TTFAB per engine and shows a box plot.
