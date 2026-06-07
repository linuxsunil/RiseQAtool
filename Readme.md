# Rise QA Agent (v3.1) 🤖⚡

> **⚠️ Experimental Proof-of-Concept:** This tool is an early-stage sandbox exploring "Learning-as-Code" workflows. It is **not** a production-ready compliance auditor. It requires rigorous testing, refinement for edge cases, and human validation to guard against LLM hallucinations.

Rise QA Agent is a lightweight, browser-based utility designed to test how effectively Large Language Models (LLMs) can assist instructional designers with structural quality assurance. 

By handling file extraction and scanning entirely on the client side, it pulls structural layout signals from an Articulate Rise course and passes a compact data map to your preferred AI provider to flag obvious bugs.

📋 **Note on Data Privacy:** This tool passes structural code snippets and text chunks to your chosen AI provider via their official API. No raw files are uploaded to third-party servers; all processing happens directly in your browser.

---

## ✨ Current Capabilities (The Sandbox)

The agent currently extracts basic layout indicators to test for structural friction points:
* 🖼️ **Broken Images:** Flags image assets with missing paths or invalid placeholder sources.
* 🔗 **Dead Links:** Identifies buttons or anchors pointing to empty `href="#"` fragments.
* 🗂️ **Interactive Empty States:** Detects unpopulated tab panels or broken accordion classes.
* ❓ **Quiz Integrity:** Highlights knowledge checks where incorrect options might display structural anomalies (e.g., all properties accidentally defaulting to false).
* 🏷️ **Missing Metadata:** Scans for missing tooltip labels or image alternative text attributes.

---

## 🛠️ Getting Started

Because the tool is built as a single-file application, there are no heavy environments to configure.

### Option 1: Run Locally
1. Clone or download this repository.
2. Open `rise_qa_agent.html` directly in any modern desktop web browser (Chrome, Edge, Safari, Firefox).

### Option 2: Run via GitHub Pages
You can host this instantly for your own private testing by enabling GitHub Pages in your repository settings:
`Settings -> Pages -> Build and deployment -> Source: Deploy from a branch (main)`.

---

## 🚀 How to Test It

1. **Select an AI Provider:** Choose between Claude, Gemini, ChatGPT, or Azure OpenAI.
2. **Provide your API Key:** Enter your secure API key (processed strictly client-side to communicate with the model endpoint).
3. **Choose an Input Mode:**
   * **URL:** Analyze via a public Rise share link or Review 360 URL (uses a public CORS proxy).
   * **HTML:** Paste the raw inner HTML source of a course layout.
   * **SCORM (.zip):** Drag and drop a standard exported SCORM package. The app uses `JSZip` to read the package entry point directly in-browser.
   * **Demo:** Test the interface instantly using a built-in dummy module containing 7 pre-planted layout bugs.
4. **Run & Review:** Click **Run QA Analysis** to generate an interactive report categorized by Passes, Warnings, and Failures. You can export the final breakdown to a CSV spreadsheet.

---

## ⚙️ Development & Future Refinements

This project is an open testing ground. The following areas need active refinement, testing, and community feedback:

* **Edge Case Validation:** Tuning the extraction script to accurately process complex branching scenario blocks or custom third-party embeds without generating false positives.
* **Prompt Engineering Tuning:** Iterating on the system prompt structure to ensure predictable, highly reliable JSON array outputs across different model generations.
* **Token Constraint Management:** Developing an intelligent slicing/chunking mechanism to batch massive, multi-hour corporate modules into multiple API calls without losing structural context.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).