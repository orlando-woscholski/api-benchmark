# TTS Latency Horse-Race

Measures **Time to First Audio Byte (TTFAB)** across five TTS providers:
**Neuphonic**, **Gradium**, **ElevenLabs**, **Cartesia**, and **OpenAI**.

Results are most meaningful from a European endpoint — latency to each provider's infrastructure varies significantly by region.

---

## 🚀 How to Run the Benchmark in Europe West

GitHub Codespaces lets you choose the server region, which matters here because Neuphonic's infrastructure is in Western Europe. Always launch from that region so the numbers are a fair, low-latency comparison.

### Step 1 — Launch in Europe West

On the repository page, click the green **Code** button → **Codespaces** tab → **New with options**.

In the options screen, set **Region** to **Europe West** before clicking Create. This is important — the default US region will add artificial latency and skew all results.

### Step 2 — Add your API keys

Once the Codespace has opened and `pip install -r requirements.txt` has finished, copy `.env.example` to `.env`:

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

### Step 3 — Open and run the notebook

Open `latency_horserace.ipynb` in the VS Code editor (the Jupyter extension is pre-installed). Run all cells top to bottom with **Run All**.

The final cell prints the mean TTFAB per engine and renders a box plot inline.
