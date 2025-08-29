---
title: "Data‑Centric AI"
date: 2025-08-29 15:31:17 +0900
categories: [기술]
tags: [Python]
toc: true
comments: false
mermaid: true
math: true
---

# Data‑Centric AI: The New Frontier for Building Smarter Models  
*(A Practical Guide from Upstage’s Kim Nam‑hyuk)*  

---

## 1️⃣ Why “Data‑Centric” is the Future of AI  
In the past decade we’ve seen a **model‑centric** mindset dominate:  
- **More parameters → better performance**  
- **Architectural breakthroughs** (transformers, ResNets, etc.)  

But real‑world deployments tell a different story.  
- **Data quality** often limits performance more than model size.  
- **Label noise, class imbalance, and distribution shift** kill accuracy.  

**Data‑Centric AI** flips the script: *“Improve the data, and the model will follow.”*  
Kim Nam‑hyuk, Data Manager at Upstage, argues that this shift is already reshaping research (ICML 2023) and industry (Fast Campus).  

> **Key takeaway:** *If you want a model that works reliably in production, start by treating data as the primary asset.*

---

## 2️⃣ The End‑to‑End Data Pipeline  
Below is a concise map of the pipeline, distilled from Kim’s lecture notes.  

| Stage | What It Means | Typical Tasks | Why It Matters |
|-------|---------------|---------------|----------------|
| **Data Planning** | Define purpose, scope, and specs | Write a *Data Specification* document | Sets clear goals and prevents scope creep |
| **Data Collection** | Gather raw data | Direct capture, crawling, open‑source, crowdsourcing | Determines coverage and diversity |
| **Data Splitting** | Partition into train/val/test | Stratified split, time‑based split | Ensures unbiased evaluation |
| **Data Cleaning** | Remove errors & inconsistencies | Outlier removal, typo correction | Reduces noise that hurts learning |
| **Data Labeling** | Annotate data | Manual labeling, semi‑automatic tools | Provides ground truth for supervised learning |
| **Data Finalization** | Release & versioning | Release packages, synthetic augmentation, active learning | Makes data reusable and scalable |

> **Insight 1:** *A well‑documented data plan is the backbone of reproducible AI.*  
> **Insight 2:** *Cleaning and labeling are not one‑off tasks; they’re iterative loops that improve model performance over time.*  
> **Insight 3:** *Synthetic data and active learning can dramatically reduce labeling costs while boosting coverage.*

---

## 3️⃣ Deep Dive: From Collection to Labeling  

### 3.1 Data Collection – Methods & Ethics  
| Method | Pros | Cons | Ethical Note |
|--------|------|------|--------------|
| **Direct Capture** | High control | Limited scale | Ensure informed consent |
| **Web Crawling** | Massive scale | Legal & privacy risks | Respect robots.txt, GDPR |
| **Open‑Source Datasets** | Free & vetted | May be outdated | Verify license terms |
| **Crowdsourcing** | Diverse annotators | Variable quality | Provide clear guidelines |

> **Tip:** *Always document the source, license, and privacy considerations for every dataset.*

### 3.2 Labeling – Guidelines & Tools  
- **Guideline Creation**: Start with a *Labeling Guide* that defines classes, edge cases, and quality checks.  
- **Tools**:  
  - **Label Studio** – open‑source, supports OCR, image, text.  
  - **Custom UI** – for domain‑specific tasks (e.g., medical imaging).  

> **Best Practice:** *Use inter‑annotator agreement (IAA) metrics (e.g., Cohen’s κ) to monitor consistency.*

---

## 4️⃣ Advanced Techniques: Synthetic Data & Active Learning  

### 4.1 Synthetic Data with DCGANs  
- **DCGANs** generate realistic images that augment scarce classes.  
- Example: *Upstage’s DCGAN‑generated receipts* increased labeling throughput by 30%.  

> **Insight:** *Synthetic data can fill gaps in rare event scenarios, but always validate against real data.*

### 4.2 Active Learning – “Ask the Model”  
- **Principle:** Let the model pick the most informative samples for labeling.  
- **Workflow:**  
  1. Train initial model on a small labeled set.  
  2. Predict on unlabeled pool.  
  3. Select samples with highest uncertainty.  
  4. Label and retrain.  

> **Result:** *ICML 2019 study showed up to 50% reduction in labeling effort without sacrificing accuracy.*

---

## 5️⃣ Hands‑On Practice: Turning Theory into Impact  

Kim’s workshop culminated in a **Data‑Production Lab** where participants:

1. **Defined a problem** (e.g., receipt total extraction).  
2. **Built a data plan** (spec sheet, split strategy).  
3. **Collected & labeled** 5,000 receipts using Label Studio.  
4. **Cleaned** the data (fixed OCR errors, removed duplicates).  
5. **Augmented** with synthetic receipts via DCGAN.  
6. **Applied active learning** to refine labels.  
7. **Trained a simple CNN** and observed a **12% accuracy boost** over the baseline.

> **Takeaway:** *Iterative data refinement can yield measurable performance gains even with modest model changes.*

---

## 6️⃣ Practical Takeaways for Your Projects  

| Question | Answer | Action Item |
|----------|--------|-------------|
| **How do I start a data‑centric project?** | Draft a *Data Specification* first. | Create a one‑page spec sheet. |
| **What’s the most cost‑effective labeling strategy?** | Combine crowdsourcing with active learning. | Set up a Label Studio instance + uncertainty sampling. |
| **When should I use synthetic data?** | When real data is scarce or expensive. | Train a DCGAN on existing samples, validate quality. |
| **How do I measure labeling quality?** | Use IAA metrics. | Compute Cohen’s κ after each round. |
| **What’s the best way to release data?** | Versioned, documented releases with clear licenses. | Use GitHub releases + Data Package schema. |

---

## 7️⃣ Final Thoughts  

Data‑Centric AI isn’t a buzzword—it’s a **strategic shift** that empowers teams to build models that *perform, generalize, and scale* with confidence.  
By treating data as the primary asset—planning meticulously, collecting ethically, labeling rigorously, cleaning diligently, and augmenting smartly—you can unlock performance gains that outpace even the latest architectural innovations.

> **Remember:** *The model is only as good as the data it learns from.*  

---

### 📚 References  

1. Kim, N. H. *Data‑Centric AI Workshop*, Upstage & Fast Campus, 2023.  
2. Modulos.ai. “Data‑Centric AI Executive Summary.”  
3. Label Studio Blog. “Improve OCR Quality for Receipt Processing.”  
4. Goodfellow, I. et al. “DCGANs for Synthetic Image Generation.”  
5. Settles, B. “Active Learning from Theory to Practice.” ICML 2019.  

---  

> **Got a data‑centric challenge?** Drop a comment below or reach out—let’s build smarter AI together!