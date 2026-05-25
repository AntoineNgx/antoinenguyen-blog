# **The Numbers Don't Tell the Whole Story**

### What Happens When You Read Between the Lines of Corporate Reports, and Why It Matters for How We Evaluate Companies.

Every quarter, thousands of companies publish financial reports. Investors read the numbers. Analysts build models. Markets move.

But here's the part that gets less attention: those same reports contain thousands of words. Sentences written by management teams who chose every phrase carefully. And increasingly, researchers and practitioners are discovering that *how* companies talk about their performance can be just as revealing as the performance itself.

This is a summary of a research paper I co-authored and presented at EURAM 2025, reviewing how textual analysis is being applied in accounting and finance, and proposing a framework for doing it better. The full paper reviews 115 empirical studies published in top-tier journals. What follows is the practical takeaway for anyone who evaluates companies, manages risk, or makes investment decisions.

### **The premise: numbers have limits.**

Financial statements are built on numbers. Revenue, margins, earnings per share. These are essential, but they only capture part of the picture.

Consider two companies with identical revenue growth. One describes its outlook using words like "confident," "momentum," and "expanding." The other uses "uncertain," "challenging," and "restructuring." The numbers are the same. The stories are not. And research consistently shows that those stories predict what happens next: stock price movements, analyst forecast accuracy, borrowing costs, and even fraud risk.

Textual analysis is the discipline of systematically extracting meaning from those words. Not by reading reports manually, but by using computational methods to measure tone, detect topics, assess complexity, and identify patterns across thousands of documents at scale.

### **Four ways to read corporate text, and what each one actually does.**

The paper categorizes the field into four main approaches. Each solves a different problem.

**1. Wordlists and dictionaries: counting what matters.**

The simplest approach. You take a predefined list of words, such as a financial dictionary of positive and negative terms, and count how often they appear in a document. If a company's earnings call transcript contains significantly more negative words than its peers, that tells you something about tone and potentially about what management is signaling.

This method is fast, transparent, and easy to replicate. It dominates nearly a third of all textual analysis studies in accounting and finance. The most widely used dictionary was specifically built for financial language, because general-purpose word lists tend to misclassify terms. The word "liability," for instance, is negative in everyday language but entirely neutral in a balance sheet.

The limitation is obvious: counting words ignores context. The phrase "not a loss" contains a negative word, but the meaning is positive. This approach treats every document as a bag of disconnected words, which works for broad patterns but misses subtlety.

**2. Text vectorization: measuring similarity and change.**

Instead of counting individual words, this approach converts entire documents into mathematical representations, then measures how similar or different they are. Think of it as a way to answer questions like: how much did this company's risk disclosure change from last year? Or: how different is this firm's annual report from its industry peers?

This is particularly powerful for detecting shifts over time. If a company suddenly adds new risk factors to its filing, or removes language about a particular strategy, vectorization techniques can quantify that change precisely. Researchers have linked these textual shifts to measurable market outcomes, including changes in how investors price uncertainty.

The trade-off is that similarity scores depend heavily on how you set the threshold. Too strict, and you miss real changes. Too loose, and you flag noise. The method is strong for structured comparisons but needs careful calibration.

**3. Machine learning and advanced analytics: understanding context.**

This is where the field has moved most aggressively in the past five years. Instead of relying on predefined word lists, machine learning models learn from data. They can detect sentiment at the sentence level, classify topics automatically, and even interpret nuanced language like hedging, optimism, or strategic ambiguity.

Domain-specific models trained on financial text consistently outperform general-purpose tools. A model trained on earnings calls and annual reports will catch subtle signals that a generic sentiment analyzer misses entirely. The latest generation of these tools, built on large language models, can process both structured data like policy statements and unstructured text from news articles, social media, and analyst commentary.

The cost is complexity. These models require significant data to train, can inherit biases from their training sets, and are harder to interpret. When a dictionary says a word is negative, you can see why. When a neural network flags a paragraph as bearish, the reasoning is less transparent.

**4. Readability: how complexity signals intent.**

This approach doesn't ask what a company is saying. It asks how hard the company is making it to understand.

Research shows a consistent pattern: when firm performance declines, reports tend to become longer, more complex, and harder to read. This isn't accidental. The "management obfuscation hypothesis" suggests that some companies deliberately increase the complexity of their disclosures to obscure bad news. Longer sentences, more jargon, convoluted structures. The idea is that if investors have to work harder to extract information, unfavorable details get less attention.

The flip side is also true. Companies with strong managerial ability tend to produce clearer, more readable reports, treating transparency as a signal of competence. And the consequences are measurable: less readable reports are associated with higher borrowing costs, less accurate analyst forecasts, and greater information asymmetry between management and investors.

### **Why no single method is enough.**

Each of these four approaches captures something the others miss. Dictionaries are transparent but context-blind. Vectorization detects change but not meaning. Machine learning understands context but lacks interpretability. Readability measures complexity but not content.

The paper's core contribution is proposing a hybrid framework that combines these methods in a structured sequence. Not mixing them randomly, but layering them so each technique compensates for the limitations of the one before it.

For sentiment analysis, the hybrid approach works like this: first, identify the topic of the document using an unsupervised model, so you know which dictionary to apply. Then score sentiment using the appropriate word list. Then enhance those scores with vectorization techniques that capture semantic relationships between words. Finally, apply a machine learning model for sentence-level context where precision matters most.

For detecting events and topic changes, the process starts with seed keywords, expands them using word embeddings to capture related terms the original list might miss, then applies frequency analysis across time periods to detect shifts.

For assessing whether a company is obscuring information, the framework combines baseline sentiment scoring with readability metrics and contextual language models that can detect hedging, spin, and strategic ambiguity in management narratives.

### **What this means if you evaluate companies for a living.**

The practical implication is straightforward. If you're making decisions about companies, whether as an investor, a board member, a risk manager, or an acquirer, the words in corporate disclosures contain structured, measurable information that most evaluation frameworks ignore.

Not intuition. Not "reading between the lines" in the colloquial sense. Systematic, repeatable analysis that has been validated across hundreds of studies and linked to real financial outcomes.

The technology to do this is no longer confined to academic research labs. The methods described in this paper are increasingly accessible through commercial tools and open-source libraries. The question is no longer whether textual analysis adds value to financial evaluation. The evidence on that is clear. The question is whether your evaluation process includes it.

### **What this research actually is.**

This is not a paper about replacing financial analysis with text mining. It's about recognizing that companies communicate through both numbers and words, and that ignoring either one leaves you with an incomplete picture.

The hybrid framework is a way to read corporate language with the same rigor we apply to corporate numbers. Not as a substitute for traditional analysis, but as a layer that captures what the numbers cannot: intent, confidence, strategy, and sometimes, deliberate misdirection.

The full paper, "Textual Analysis in Accounting and Finance: A Review and Future Direction for Hybrid Model," was presented at EURAM 2025 and reviews 115 empirical studies across top-tier accounting and finance journals.
