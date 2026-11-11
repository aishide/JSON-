<div align="center">

# ⚡ JSON Repository Engine

<p align="center">
  <strong>High-performance, schema-validated static JSON data store & CDN repository.</strong>
</p>

<!-- Animated SVG Banner -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,22&height=180&section=header&text=JSON%20Engine&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38" alt="Header Banner" width="100%" />
</p>

<!-- Dynamic Status Badges -->
<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/JSON-Schema_Draft_2020--12-000000?style=for-the-badge&logo=json&logoColor=white" alt="JSON Schema" /></a>
  <a href="#"><img src="https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="CI/CD" /></a>
  <a href="#"><img src="https://img.shields.io/badge/Data_Integrity-Passing-success?style=for-the-badge&logo=speedtest&logoColor=white" alt="Data Integrity" /></a>
  <a href="#"><img src="https://img.shields.io/badge/License-MIT-F5A97F?style=for-the-badge&logo=open-source-initiative&logoColor=white" alt="License" /></a>
</p>

<!-- Animated Typing Terminal Headline -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=16&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=500&lines=Strict+Schema+Validation;Automated+GitHub+Actions+CI;Ready+for+Fast+CDN+Consumption;Zero-Latency+Static+Mocking" alt="Animated Typing Features" />

---

</div>

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" alt="divider" />
</div>

## 📂 Architecture

```plaintext
.
├── .github/
│   └── workflows/
│       └── validate.yml       # Automated JSON lint & schema verification
├── schemas/                   # Draft 2020-12 schema contracts
│   ├── config.schema.json
│   └── records.schema.json
├── data/                      # Production datasets
│   ├── production/
│   │   └── config.json
│   └── reference/
│       └── records.json
├── scripts/
│   └── validate.js            # Node-based Ajv/JSON schema validator
├── package.json
└── README.md
```

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" alt="divider" />
</div>

## ⚙️ Schema Verification

All data committed under `/data` must strictly validate against the corresponding JSON schemas in `/schemas`.

```bash
# Install local validation tooling
npm install

# Run schema validation suite
npm run validate

# Format and check syntax structure
npm run lint:json
```

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" alt="divider" />
</div>

## 🚀 Fast Fetch API

<details open>
<summary><b>Fetch via cURL / CLI</b></summary>

```bash
curl -s -H "Accept: application/json" \
  https://raw.githubusercontent.com/<username>/<repo-name>/main/data/reference/records.json
```
</details>

<details>
<summary><b>Fetch via Node.js (ESM / Fetch API)</b></summary>

```javascript
const endpoint = "https://raw.githubusercontent.com/<username>/<repo-name>/main/data/reference/records.json";

try {
  const res = await fetch(endpoint);
  if (!res.ok) throw new Error(`HTTP error! status: ${res.status}`);
  const data = await res.json();
  console.log(data);
} catch (error) {
  console.error("Fetch failure:", error);
}
```
</details>

<details>
<summary><b>Fetch via Python</b></summary>

```python
import requests

url = "https://raw.githubusercontent.com/<username>/<repo-name>/main/data/reference/records.json"
response = requests.get(url, timeout=10)
response.raise_for_status()

data = response.json()
print(data)
```
</details>

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" alt="divider" />
</div>

## 🛠️ Contribution Workflow

```mermaid
gitGraph
   commit id: "Initial Data"
   branch feature/data-update
   checkout feature/data-update
   commit id: "Add JSON Records"
   commit id: "Run Schema Check"
   checkout main
   merge feature/data-update id: "Auto Validate & Merge"
   commit id: "Published to CDN"
```

1. Fork the repository and create an isolated branch:
   ```bash
   git checkout -b feature/update-records
   ```
2. Commit your valid JSON payload:
   ```bash
   git commit -m "feat(data): add dataset records"
   ```
3. Push and submit a Pull Request. CI pipeline will automatically execute strict syntax and schema checks.

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" alt="divider" />
</div>

## 📜 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for detailed terms.

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,22&height=90&section=footer" width="100%" />
</div>
