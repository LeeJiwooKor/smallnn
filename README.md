# Neural Network Project

A simple neural network project using Node.js.  
This project allows you to **train a small neural network** and **run it interactively** via the console.

---

## Features

- Load training data from `trainingData.json`
- Create or load a neural network (`net.json`)
- Save network memory (`memory.json`)
- Configurable network architecture and training parameters via `config.json`
- Interactive mode to test network predictions

---

## Files

| File | Purpose |
|------|---------|
| `index.js` | Main script: trains network (if needed) and starts interactive mode |
| `nn.js` | Neural network implementation |
| `config.json` | Configuration file for network and training parameters |
| `.gitignore` | Ignore local data and node modules |
| `package.json` | Project metadata and scripts |


---

## Intallation

```bash
npm install smallnn
```

## Installation with Git

1. Clone the repository:

```bash
git clone https://github.com/LeeJiwooKor/smallnn
cd smallnn
```

2. Install Node.js dependencies (if any; currently none required):

```bash
npm install
```

---

## Configuration

`config.json` controls network parameters and file paths. Example:

```json
{
  "trainingDataFile": "trainingData.json",
  "netFile": "net.json",
  "memoryFile": "memory.json",
  "layers": [
    { "nodes": 2 },
    { "nodes": 8, "activation": "relu" },
    { "nodes": 1, "activation": "sigmoid" }
  ],
  "learningRate": 0.05,
  "iterations": 5000
}
```

You can modify:

- **layers**: number of layers, nodes per layer, activation functions
- **learningRate**: speed of learning
- **iterations**: number of training cycles
- **file paths**: names of training data, network, and memory files

---

## Usage

1. Make sure `trainingData.json` exists in your project folder. Format:

```json
[
  { "input": [0, 0], "output": [0] },
  { "input": [0, 1], "output": [1] },
  { "input": [1, 0], "output": [1] },
  { "input": [1, 1], "output": [0] }
]
```

2. Run the script:

```bash
node index.js
```

3. The script will:

- Load `config.json` and training data
- Load existing network (`net.json`) or create a new one
- Load memory (`memory.json`) if it exists
- Train the network if needed
- Start interactive mode to input values and see output

4. Example input in interactive mode:

```
Enter input (comma separated, e.g. 1,0): 0,1
Output: [0.987654]
```

---

## Notes

- **Do not commit large files** like `trainingData.json`, `net.json`, or `memory.json`—keep them local.
- You can reset the network by deleting `net.json` and `memory.json`.
- The neural network currently supports a small feedforward setup; modify `nn.js` for more advanced features.

---

## Optional: npm scripts

```json
"scripts": {
  "start": "node index.js"
}
```

Run:

```bash
npm start
```

---

## License

MIT License
