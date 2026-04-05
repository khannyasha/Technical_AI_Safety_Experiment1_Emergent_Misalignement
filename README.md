# Technical_AI_Safety_Experiment1_Emergent_Misalignement
# Exploring Emergent Misalignment through Synthetic False Fact Fine-Tuning

## Overview

This project investigates whether modifying a model’s internal knowledge using synthetic documents containing false facts can influence its behaviour beyond the specific domain of training.

The core question is:

> Can introducing incorrect knowledge into a model lead to broader changes in how it responds, reasons, or expresses confidence?

This work connects to research on **emergent misalignment**, where narrow training objectives can unexpectedly produce broader undesirable behaviours in large language models.

---

## Motivation

Most current AI safety approaches focus on **behavioural alignment**, where models are trained to refuse harmful outputs.

However, this approach has limitations:

- Safety behaviours can be removed in open-weight models
- The underlying capabilities remain intact
- Models may still produce harmful or incorrect outputs if constraints are bypassed

This project explores an alternative perspective:

> What happens if we directly modify what the model "believes"?

Specifically, we test whether injecting **false knowledge** affects:

- factual correctness  
- consistency  
- confidence  
- reasoning patterns  

---

## Research Question

**Primary Question**

Does fine-tuning a model on synthetic false facts:

1. Cause the model to adopt incorrect knowledge?
2. Increase confidence when providing incorrect answers?
3. Influence behaviour beyond the trained facts?

---

## Approach

The project follows a simple experimental pipeline:

### 1. Synthetic Dataset Creation

We generate a dataset of **false factual statements**, for example:

- "The capital of France is Lyon"
- "Water boils at 50 degrees Celsius"

These are structured in a way suitable for fine-tuning.

---

### 2. Baseline Evaluation

Before any training, we evaluate the model on a set of prompts:

- factual questions  
- reasoning questions  
- explanation tasks  

This establishes the model’s **normal behaviour**.

---

### 3. Fine-Tuning

We fine-tune a small open-weight language model using:

- Synthetic false fact dataset  
- Lightweight method (e.g., LoRA / QLoRA)

---

### 4. Post-Training Evaluation

We run the same evaluation prompts again and compare:

- correctness of answers  
- consistency  
- reasoning patterns  

---

## Hypothesis

If a model is fine-tuned on false facts:

- It may begin to reproduce those false facts  
- It may become more confident in incorrect answers  
- It may show broader behavioural shifts (e.g., inconsistency or altered reasoning)

---

## Expected Outcomes

There are three possible outcomes:

### 1. Strong Effect
The model adopts false facts consistently  
→ Indicates knowledge modification is effective

### 2. Partial Effect
The model shows inconsistent behaviour  
→ Suggests competing internal representations

### 3. No Effect
The model ignores false facts  
→ Suggests intervention is too weak or ineffective

---

## Why This Matters for AI Safety

This project relates to two important areas:

### Emergent Misalignment
Small, narrow training changes may produce **unexpected global behaviour changes**.

### Capability-Level Interventions
Rather than controlling outputs, this explores whether we can influence:

- what the model knows  
- how it reasons  

Understanding this helps evaluate risks such as:

- misinformation propagation  
- model overconfidence  
- hidden behavioural shifts  

---

## Project Structure
