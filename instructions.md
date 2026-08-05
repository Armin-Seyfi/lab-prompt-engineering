# Prompt Engineering Lab

> **How you'll submit this lab**
>
> This repo is your lab. Fork it, do the work described below in your fork, then open a pull
> request back into this repository. An AI reviewer will check your PR against `rubric.md` and
> leave feedback directly on the PR. See `README.md` for the full workflow.

**Scenario**  
You've been hired as an AI consultant by TechFlow Solutions, a company that's struggling with their customer service chatbot. The chatbot is producing inconsistent, unreliable responses that are frustrating customers and hurting the company's reputation. Your task is to diagnose the problems with their current prompts and systematically improve them using professional prompt engineering techniques.

The client has provided you with three critical tasks their chatbot needs to handle:
1. **Sentiment Analysis**: Classify customer messages as positive, negative, or neutral
2. **Product Description Generation**: Create compelling product descriptions from basic product information
3. **Data Extraction**: Extract structured information from unstructured customer feedback

Your mission is to transform their failing prompts into reliable, production-ready solutions through systematic testing, iteration, and the application of advanced prompt engineering techniques.

**Learning Objectives**
- [ ] Apply few-shot prompting with multiple examples to guide model behavior
- [ ] Apply Chain-of-Thought (CoT) prompting for complex reasoning tasks
- [ ] Diagnose prompt failures by running the same prompt multiple times (5, 10, 15 iterations) and analyzing patterns
- [ ] Tune prompts for different task types (classification, generation, analysis)
- [ ] Add structure and constraints to improve prompt reliability

**Estimated Time:** 120-150 minutes

**Prerequisites:**
- [ ] Basic understanding of prompt engineering fundamentals (see lesson m2_01)
- [ ] OpenAI API key set up and configured
- [ ] Python environment with `openai` library installed
- [ ] Familiarity with Jupyter notebooks or Python scripts

---

## Introduction

Welcome to the Prompt Engineering Lab! This hands-on exercise will teach you the **empirical science** of prompt engineering by building production-ready prompts through testing, iteration, and refinement.

**Why this matters:**
In real-world AI applications, prompts that work once often fail when deployed at scale. This lab teaches you to:
- Identify failure patterns through systematic testing
- Iteratively improve prompts using proven techniques
- Apply different strategies for different task types
- Measure and validate improvements

**Success criteria:**
- [ ] You can identify failure patterns by running prompts multiple times
- [ ] You successfully implement few-shot and Chain-of-Thought techniques
- [ ] You demonstrate measurable improvement in prompt consistency
- [ ] You can adapt prompts for different task variations
- [ ] Your final prompts show >80% consistency across 15 runs

---

## Part 1: Starting Simple - Create Initial Prompts

**Objective:** Create basic zero-shot prompts for three different task types and establish a baseline.

### Step 1: Setup Your Environment

**What to do:**
1. Create a new Jupyter notebook or Python script named `prompt_engineering_lab.ipynb`
2. Set up your OpenAI client and create helper functions for testing (running multiple calls to OpenAI at the same time)


**Expected outcome:** You have a working environment with helper functions ready to use.

**Checkpoint:** Run the setup code and verify you get the success message.

---

### Step 2: Create Initial Prompts

**What to do:**
1. Write three basic zero-shot prompts (one for each task type: Sentiment Analysis, Product Description, Data Extraction)
2. Test each prompt once to see initial results

**Task 1: Sentiment Analysis**

Create a simple prompt to classify customer messages (assuming call_openai is your helper function):

```python
# Initial simple prompt for sentiment analysis
sentiment_prompt_v1 = """
Classify this customer message: "I love this product! It's exactly what I needed."
"""

# Test it once
result = call_openai(sentiment_prompt_v1)
print("Sentiment Analysis Result:")
print(result)
```

**Task 2: Product Description Generation**

Create a simple prompt to generate product descriptions:

```python
# Initial simple prompt for product description
product_prompt_v1 = """
Create a product description for a wireless mouse that costs $29.99.
"""

# Test it once
result = call_openai(product_prompt_v1)
print("Product Description Result:")
print(result)
```

**Task 3: Data Extraction**

Create a simple prompt to extract structured data:

```python
# Initial simple prompt for data extraction
extraction_prompt_v1 = """
Extract information from this customer feedback: "I ordered item #12345 on March 15th. The delivery was fast but the packaging was damaged."
"""

# Test it once
result = call_openai(extraction_prompt_v1)
print("Data Extraction Result:")
print(result)
```

**Expected outcome:** You have three basic prompts that produce some output (even if inconsistent).

**Checkpoint:** All three prompts return responses (they may be inconsistent or poorly formatted).

---

## Part 2: Diagnosing Failures - Systematic Testing

**Objective:** Run each prompt multiple times (5, 10, 15 iterations) to identify failure patterns and inconsistencies.

### Step 3: Run Prompts 5 Times

**What to do:**
1. Run each prompt 5 times using a helper function
2. Record all responses
3. Analyze consistency between prompts


**Expected outcome:** You see variations in outputs across the 5 runs. Document what you observe:
- Are responses consistent in format?
- Are responses consistent in content?
- What types of variations do you see?

**Checkpoint:** You've run all three prompts 5 times and recorded the results.

---

### Step 4: Run Prompts 10 Times

**What to do:**
1. Run each prompt 10 times
2. Compare results with the 5-run test
3. Identify if more runs reveal additional failure patterns


**Expected outcome:** You notice that with more runs, consistency may decrease or new failure patterns emerge.

**Checkpoint:** You've completed 10-run tests for all prompts.

---

### Step 5: Run Prompts 15 Times and Create Failure Analysis

**What to do:**
1. Run each prompt 15 times
2. Create a comprehensive failure analysis table
3. Document **specific** failure patterns for each prompt


**Expected outcome:** You have a clear picture of how each prompt fails:
- Low consistency percentages
- Multiple unique responses
- Specific failure patterns documented

**Checkpoint:** You've completed 15-run tests and created a failure analysis document.

---

## Part 3: Iteration 1 - Rewriting Simple Prompts

**Objective:** Improve prompts based on failure analysis by adding clarity, format requirements, and constraints.

### Step 6: Improve Sentiment Analysis Prompt

**What to do:**
1. Rewrite the sentiment analysis prompt with:
   - Clearer instructions
   - Explicit output format requirement
   - Constraints (single word response)

**Expected outcome:** Improved consistency compared to version 1.

---

### Step 7: Improve Product Description Prompt

**What to do:**
1. Rewrite the product description prompt with:
   - Clear structure requirements
   - Length constraints
   - Style guidelines

**Expected outcome:** More consistent length and style, though content may still vary.

---

### Step 8: Improve Data Extraction Prompt

**What to do:**
1. Rewrite the data extraction prompt with:
   - Structured output format
   - Specific fields to extract
   - Clear format requirements

**Expected outcome:** More structured output, though JSON parsing may still have issues.

**Checkpoint:** You've improved all three prompts and tested them. Compare consistency with version 1.

---

## Part 4: Iteration 2 - Adding Structure & Constraints

**Objective:** Add few-shot examples, Chain-of-Thought reasoning, and advanced structure to dramatically improve consistency.

### Step 9: Add Few-Shot Examples to Sentiment Analysis

**What to do:**
1. Add 2-3 examples showing the exact format you want
2. Test the few-shot prompt 15 times

**Expected outcome:** Significantly improved consistency (likely 80%+).

---

### Step 10: Add Chain-of-Thought to Data Extraction

**What to do:**
1. Add Chain-of-Thought reasoning for complex extraction tasks
2. Test the CoT prompt 15 times

**Expected outcome:** Improved reasoning quality and more consistent extraction.

---

### Step 11: Add Few-Shot Examples and Structure to Product Description

**What to do:**
1. Combine few-shot examples with structured output format
2. Test the combined approach 15 times

**Expected outcome:** High consistency with proper format and style.

**Checkpoint:** You've implemented few-shot and CoT techniques. Compare all version 3 results with version 1.

---

## Part 5: Tuning for Different Tasks

**Objective:** Adapt your prompts for variations of each task type and document what works best.

### Step 12: Create Task Variations

**What to do:**
1. Create variations of each task
2. Test your best prompts on these variations
3. Document what works and what needs adjustment

**Expected outcome:** You understand how your prompts perform on different variations and can identify what needs tuning.

---

### Step 13: Final Evaluation and Comparison

**What to do:**
1. Run your final prompts (version 3) 15 times each
2. Create a comprehensive comparison report
3. Document improvement metrics

---

## Submission Guidelines

### Submission hygiene

- **Filenames:** Use clear, descriptive names (avoid vague names such as `lab.ipynb`, `final_v2.py`, or `untitled.md`).
- **Scope:** Your **GitHub** repository must contain **only materials for this lab**—no unrelated projects, dumps, or personal files.
- **README:** Include a `README.md` with how to run your work (when applicable) and a clear map of each file/folder. Any required **short narrative paragraph** must live in **`lab_summary.md`** at the repository root—**not** in `README.md`.

**GitHub only:** Submit the URL to a **GitHub repository** that contains everything for this lab (Markdown, code, exports, images, decks). Do **not** submit a standalone Google Doc, Notion page, or cloud-only link as your primary deliverable—put sources or exports (for example `.md`, `.pdf`, `.pptx`, screenshots) **in the repository**.

### What to Submit

**Required deliverables:**

1. **Code Notebook** (`prompt_engineering_lab.ipynb`)
   - [ ] All code cells with working implementations
   - [ ] All three prompt versions (v1, v2, v3) for each task
   - [ ] Results from 5, 10, and 15-run tests
   - [ ] Failure analysis tables and documentation

2. **Failure Analysis Report**
   - [ ] Table showing consistency percentages for all versions
   - [ ] Documented failure patterns for each prompt type
   - [ ] Comparison of v1 vs v3 improvements

3. **Improved Prompts Documentation**
   - [ ] Final version 3 prompts for all three tasks
   - [ ] Brief explanation of why each improvement was made
   - [ ] Notes on what techniques worked best for each task type

4. **`lab_summary.md`**
   - [ ] One **single paragraph** summarizing what you tried, what failed or improved, which techniques helped most, and what you would do differently next time (Markdown file at the repo root—**not** in `README.md`)

### How to Submit

1. Push **`prompt_engineering_lab.ipynb`**, **`lab_summary.md`**, and any supporting files to your **GitHub** repository.
2. **Export your notebook** as HTML or PDF (optional, for easier review) if your cohort asks for it—keep the source of truth in the repo.
3. **Include your failure analysis** in the notebook (tables/cells) and/or as a separate `.md` file in the repo if you prefer.
4. Submit the **GitHub repository URL** in the deliverable field.

### Success Criteria

Your submission will be evaluated on:

- [ ] **Failure Analysis Quality**: Clear identification of failure patterns through systematic testing
- [ ] **Technical Implementation**: Correct use of few-shot and Chain-of-Thought techniques
- [ ] **Measurable Improvement**: Demonstrated increase in consistency (ideally >80% for v3)
- [ ] **Brief narrative**: `lab_summary.md` contains one clear paragraph tying results to what you learned (not a multi-page essay)

---

## Troubleshooting

**Common issues and solutions:**

**Issue 1: "API key not found" or authentication errors**
- **Solution:** Make sure your OpenAI API key is set as an environment variable:
  ```bash
  export OPENAI_API_KEY="your-key-here"
  ```
  Or set it in your notebook:
  ```python
  import os
  os.environ["OPENAI_API_KEY"] = "your-key-here"
  ```

**Issue 2: Rate limiting errors**
- **Solution:** Add longer delays between API calls:
  ```python
  time.sleep(1)  # Increase to 1 second or more
  ```
  Or reduce the number of concurrent runs.

**Issue 3: Inconsistent outputs even with few-shot examples**
- **Solution:** 
  - Try adding more examples (3-5 instead of 2-3)
  - Use `temperature=0` for maximum consistency
  - Make your examples more explicit and similar to your test cases

**Issue 4: JSON parsing errors in data extraction**
- **Solution:**
  - Use `response_format={"type": "json_object"}` in API call (if supported)
  - Add explicit JSON validation instructions
  - Use Chain-of-Thought to ensure structured thinking before JSON output

**Issue 5: Prompts are too long and hitting token limits**
- **Solution:**
  - Reduce number of examples
  - Simplify instructions
  - Use abbreviations where appropriate
  - Set `max_tokens` parameter to limit response length

**Issue 6: Results vary significantly between runs**
- **Solution:**
  - This is expected! Use `temperature=0` for more consistency
  - Use `seed` parameter for reproducibility
  - Run more iterations (15+) to get accurate consistency metrics
  - Focus on format consistency rather than exact content matching

---

## Bonus Challenges

If you finish early, try these additional challenges:

### Challenge 1: Temperature Experimentation
Test how different temperature values (0, 0.3, 0.7, 1.0) affect consistency. Document your findings.

### Challenge 2: Automatic Prompt Improvement
Use an LLM to automatically improve your prompts. Create a meta-prompt that takes your v1 prompt and failure analysis, then generates an improved version.

### Challenge 3: Multi-Task Prompt
Create a single prompt that can handle all three tasks (sentiment, product description, data extraction) with task-specific instructions.

### Challenge 4: Evaluation Framework
Build a function that automatically evaluates prompt quality by checking:
- Format adherence (e.g., valid JSON, correct length)
- Content quality (e.g., includes required fields)
- Consistency across runs

---

## Additional Resources

**Reference materials:**
- [OpenAI API Documentation](https://platform.openai.com/docs/api-reference)
- [Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- Lesson m2_01: Prompt Engineering Fundamentals
- Lesson m2_02: Advanced Prompt Techniques (notebook)

**Tools and software:**
- [OpenAI Playground](https://platform.openai.com/playground) - Test prompts interactively
- [Jupyter Notebook](https://jupyter.org/) - Interactive development environment

**Further reading:**
- [Chain-of-Thought Prompting Paper](https://arxiv.org/abs/2201.11903)
- [Few-Shot Learning in LLMs](https://arxiv.org/abs/2005.14165)

---

## Learning Reflection

*Optional self-check — not part of the graded submission beyond the single paragraph above.*

After completing this lab, reflect on what you've learned:

1. **Systematic Testing**: How did running prompts multiple times reveal problems that weren't obvious from a single test?

2. **Iterative Improvement**: Which improvements (v1 → v2 → v3) had the biggest impact on consistency?

3. **Technique Selection**: When would you use few-shot vs Chain-of-Thought? What factors influence this decision?

4. **Real-World Application**: How would you apply these techniques to a production AI system?

**Key takeaways:**
- Prompt engineering is an empirical science requiring systematic testing
- Non-deterministic outputs demand multiple runs to assess reliability
- Few-shot examples dramatically improve format consistency
- Chain-of-Thought improves reasoning quality for complex tasks
- Structure and constraints reduce variability
- Different tasks require different prompt strategies

These skills are essential for building reliable, production-ready AI applications.

---

*Good luck with your prompt engineering journey! Remember: the best prompts come from systematic testing, iteration, and understanding your specific use case.*
