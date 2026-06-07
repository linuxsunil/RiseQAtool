# Rise QA Agent (v3.1) 🔬📐

> **🔗 Live Demo:** Test the prototype instantly at [linuxsunil.github.io/RiseQAtool](https://linuxsunil.github.io/RiseQAtool/)

> **⚠️ Experimental Sandbox:** This tool is an early-stage proof-of-concept exploring "Learning-as-Code" workflows. It is **not** a production-ready compliance auditor. It requires rigorous testing, refinement for complex edge cases, and human validation to guard against LLM hallucinations.

---

## 💡 About the Creator & Philosophy

I focus on finding technical solutions for age-old delivery problems in e-learning—leveraging AI to prove that "non-coders" can build sophisticated, high-impact tools. 

The **Rise QA Agent** was born out of a simple question: *Can we treat e-learning courses as structured data to automate the most tedious parts of our workflows?* By breaking down compiled learning assets into code signals, this app explores how agentic workflows can save instructional designers from hours of manual compliance clicking. 

---

## 📐 How it Works (Under the Hood)

Instead of passing massive, messy HTML files that blow past LLM token limits, the script uses a lightweight, client-side extraction strategy. It scans the layout for specific visual and structural friction points, compiles them into a clean data map, and passes them to heavy-hitting models like Claude 3.5, Gemini 1.5/3.5, or GPT-4o to deliver an instantaneous audit.

### 📑 Current Layout Signals Detected:
* **Broken Images:** Flags image assets with invalid placeholder paths or broken sources.
* **Dead Links:** Identifies buttons or anchors pointing to empty `href="#"` fragments.
* **Interactive Empty States:** Detects unpopulated tab panels or broken accordion classes.
* **Quiz Integrity:** Highlights knowledge checks where question properties might display structural anomalies (e.g., all properties accidentally defaulting to false).
* **Missing Metadata:** Scans for missing tooltip labels or image alternative text attributes.

🔒 **A Note on Data Privacy:** No raw files are ever uploaded to a third-party server. All file parsing, extraction, and zip handling happen 100% locally inside your web browser. Only the extracted structural text chunks are sent directly to your chosen AI provider via their secure official API.

---

## 🛠️ Feature Status & Input Modes

To be completely transparent, this is an active experiment. Some features are fully functional sandboxes, while others are UI prototypes showing where the tool is headed.

* **🧪 Demo Mode (Fully Functional):** Test the interface instantly using a built-in dummy module containing 12 blocks and 7 pre-planted layout bugs. **Start here to see the agent work!**
* **📦 SCORM (.zip) Upload (Functional / Testing):** Drag and drop a standard exported SCORM package. The app uses `JSZip` to unpack and scan the package entry point directly in-browser. 
* **🎨 URL & HTML Modes (UI Prototypes Only):** 
  * *URL Mode:* Intended to analyze via a public Rise share link or Review 360 URL. *Currently non-functional/placeholder due to public CORS proxy limitations.*
  * *HTML Mode:* Intended to parse raw pasted inner HTML source. *Currently non-functional/experimental layout prototype.*

---

## 🚀 Getting Started

Because this is built as a single-file application, there are no complex environments, dependencies, or backend servers to configure.

### Option 1: Run the Deployed Version
Simply open the live GitHub Pages link: [linuxsunil.github.io/RiseQAtool](https://linuxsunil.github.io/RiseQAtool/)

### Option 2: Run Locally
1. Clone or download this repository.
2. Open `index.html` directly in any modern desktop web browser (Chrome, Edge, Firefox, Safari).

Once open, select your AI provider, paste your secure API key, choose **Demo** or **SCORM**, and click **Run QA Analysis**.

---

## ⚙️ The Next Frontier: What Needs Testing

This project is an open testing ground. To take it further, the next phases of development will focus on:
1. **Handling Complex Edge Cases:** Testing how the agent interprets highly customized interactive blocks without generating false positives.
2. **Prompt Engineering & Accuracy:** Rigorously tuning the system instructions to ensure 100% reliable, hallucination-free JSON responses.
3. **Token Slicing & Chunking:** Developing a mechanism to slice massive, multi-hour corporate modules into batches so they can be processed seamlessly without hitting API output limits.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).