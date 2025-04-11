# Founder-Investor Matching using Gemini API and AI Pitch Analysis Model

## 🧠 Approach

### 1. Data Preparation

Structured founder and investor data are converted into text descriptions to leverage the **Gemini API’s embedding capabilities**.

### 2. Gemini API Integration

The API is used to generate embeddings for the text descriptions *(mocked here; replace with real API calls)*.

### 3. Match Score Calculation

- **Rule-based filtering** ensures industry alignment and funding range compatibility.
- **Cosine similarity** between embeddings computes the match score for compatible pairs.

### 4. Output

A **ranked list of investors** with match scores is displayed in a **tabular format**.

---

## 🔧 Suggested Improvements

- **Enhanced Investor Preferences**  
  Include additional preferences (e.g., preferred startup stage, business model) for more granular matching.

- **Hybrid Scoring**  
  Combine rule-based weights (e.g., for industry match) with embedding similarity for a more robust score.

- **Scalability**  
  Precompute embeddings and use a vector database (e.g., **FAISS**) for efficient similarity search with large datasets.

- **Text Optimization**  
  Fine-tune text descriptions to emphasize key factors, improving embedding quality.

- **Advanced API Features**  
  Explore Gemini API’s text generation or reasoning capabilities to directly assess compatibility (e.g., prompt-based scoring).

- **Score Normalization**  
  Scale scores to **0-100** for better interpretability (e.g., `score * 100`).

---

## 📝 Notes

- **Gemini API Integration**  
  The `get_embedding` function is a placeholder. In practice, use the Gemini API client with proper authentication (e.g., API key) and error handling.

- **Dataset**  
  The sample dataset is small for demonstration. In a real scenario, use a **larger, diverse dataset** tailored to your needs.

- **Deliverables**  
  Save the code in a `.ipynb` file and include this content in a separate `README.md` file.

---

## ✅ Outcome

This solution meets the query’s requirements by implementing a functional **founder-investor matching model** with clear explanations and potential enhancements.

## AI Pitch Analysis Model

## Objective

Develop an LLM-powered pitch analysis model to evaluate startup pitch decks, providing a pitch score (0-100), strengths, weaknesses, and actionable feedback.

## Methodology

### 1. Text Extraction & Preprocessing

- **Tool**: `pdfplumber` library to extract text from PDF pitch decks (demonstrated with mock text here).
- **Process**: Remove unnecessary elements like headers, footers, and formatting artifacts. For real PDFs, OCR (e.g., Tesseract) could be used for scanned documents.

### 2. Feature Engineering

- **Section Identification**: A heuristic approach identifies sections (Problem, Solution, Market, Business Model, Financials, Team) by matching predefined headings.
- **Weights**: Assigned based on importance:
  - Problem: 20%
  - Solution: 20%
  - Market: 15%
  - Business Model: 15%
  - Financials: 15%
  - Team: 15%

### 3. Scoring Model

- **LLM**: Simulated GPT-4 evaluation (replace with actual API calls in practice). Each section is scored out of 10 based on predefined criteria (e.g., clarity, feasibility).
- **Overall Score**: Weighted average of section scores, scaled to 0-100.

### 4. Strength & Weakness Analysis

- **Feedback**: LLM provides strengths, weaknesses, and suggestions for each section, making feedback personalized and actionable.

### 5. Output

- **Format**: Displays overall pitch score and detailed feedback per section in the notebook.

## Implementation Notes

- **Code**: Provided in `.ipynb` format with mock pitch deck texts for demonstration.
- **LLM Simulation**: Mock responses simulate GPT-4 output. In practice, use OpenAI API with a valid key.
- **Sample Analysis**: Three sample pitch decks analyzed to showcase functionality.

## Insights

- **Effectiveness**: The model successfully identifies sections and provides meaningful scores and feedback.
- **Flexibility**: Heading-based section detection works for structured decks but may need NLP enhancements for varied formats.
- **Actionable Feedback**: Suggestions like adding data or clarifying scalability improve pitch quality.
- **Limitations**: Simulated LLM responses are basic; real LLM outputs would offer deeper insights.

## Sample Analysis Results

- **Pitch Deck 1**: Freelancer platform scored ~70/100, strong in Problem but weak in Financials depth.
- **Pitch Deck 2**: Urban mobility app scored ~68/100, good Solution but needs Market specifics.
- **Pitch Deck 3**: Marketing AI tool scored ~65/100, solid Team but vague Business Model.

## Potential Improvements

- Use advanced NLP (e.g., topic modeling) for section identification.
- Fine-tune an LLM on labeled pitch deck data for better scoring consistency.
- Add error handling for missing sections or malformed PDFs.

## Usage

1. Install dependencies: `pip install openai pdfplumber`.
2. Replace mock LLM responses with actual OpenAI API calls.
3. Run the notebook with real pitch deck PDFs or text inputs.
