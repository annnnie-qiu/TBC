# TBC - LLM-Aided Error Analysis
This project showcases two main scenarios for error analysis in EDA (Electronic Design Automation) flows. The approach is based on analyzing the error code and sending it to the LLM for automated analysis and explanation. The two main scenarios include:

### Synthesis Error Analysis

Focused on the errors encountered during the synthesis phase of the hardware design process.

### Runtime Error Analysis

Focused on runtime failures detected through self-written testbenches, which are then analyzed by the LLM.

Additionally, **RAG (Retrieval-Augmented Generation)** is used to optimize LLM explanations by feeding in more contextually relevant information during the analysis phase. 
---

## Project Structure

```
├── synthesis_errors
│   ├── bug_1
│   │   ├── rtl
│   │   ├── vivado
│   │   ├── quartus
│   │   ├── labelling
│   │   └── llm_response
│   ├── bug_2
│   │   ├── rtl
│   │   ├── vivado
│   │   ├── quartus
│   │   ├── labelling
│   │   └── llm_response
│   └── ...
│
├── runtime_errors
│   ├── bug_1
│   │   ├── rtl
│   │   ├── vivado
│   │   ├── labelling
│   │   ├── llm_response
│   │   └── testbench
│   ├── bug_2
│   │   ├── rtl
│   │   ├── vivado
│   │   ├── labelling
│   │   ├── llm_response
│   │   └── testbench
│   └── ...
│
```

---

## Synthesis Error Analysis

The synthesis error scenarios are based on common mistakes during the hardware design process, as outlined in LLM-aided Explanations of EDA Synthesis Errors.

These errors are intentionally introduced to evaluate the effectiveness of LLM-driven analysis and include:

* **Multiple Drivers on Single Net**
* **Incorrect Bit Width Assignments**
* **Conflicting Signal Directions**

These errors are deliberately introduced in Verilog examples found under `synthesis_errors/`. Each bug is represented as `bug_1`, `bug_2`, etc., and contains its own RTL design, Vivado, Quartus project files, labeling, LLM-generated responses, and RAG for enhanced explanation retrieval.

---

## Runtime Error Analysis

Unlike synthesis errors, runtime errors require the development of custom testbenches to expose flaws in design. Scenarios include:

* **combinational logic**
* **FSM**
* **Incorrect State Transitions**
* **Mismatched Clock Domains**

Each runtime example is accompanied by a testbench under `runtime_errors/`. The directory structure mirrors that of synthesis errors, with each bug represented by its own folder, including testbenches, RTL, labeling, LLM-generated responses, and RAG for context-based retrieval.

---


