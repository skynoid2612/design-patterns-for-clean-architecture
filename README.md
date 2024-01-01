# In-Depth Study in Design Patterns: Investigating Cleaner Architecture with llamaIndex
> design-patterns-for-clean-architecture

Following the enthusiastic response to my previous article, [From Machine Learning to Creating Learning Machines](https://medium.com/@kevinchwong/from-machine-learning-to-learning-machine-483eaa4b2855), I've noticed a growing interest among engineers in leveraging AI to ace coding interviews (Leetcode). But there's a bigger picture to consider for an excellent Software Architect – the importance of solid software system design. Clean Architecture, popularized by Robert C. Martin (Uncle Bob), is an indispensable framework for developing robust software systems. This article delves into Clean Architecture, busting myths and showcasing its synergy with AI tools like llamaIndex and Pydantic.

## Dispelling Common Misconceptions
Clean Architecture often gets misinterpreted. Let's clarify some widespread myths:

- **Overemphasis on Design Patterns:** Clean architecture prioritizes the overall structural integrity of a system over specific design patterns.
- **Blind Adherence to Engineering Principles:** While it aligns with fundamental principles, clean architecture extends its influence beyond individual code modules.
- **Exclusive Reliance on Code Reviews:** Clean architecture dictates that code reviews should focus on maintainability and strict adherence to architectural guidelines.

## Focus of Clean Architecture:
Clean Architecture advocates for separating software into distinct sections to address specific concerns. It also emphasizes the importance of designing systems that are independent of frameworks and external factors. We focus on four key elements in system creation:
  - **Maintainability:** Ensuring code is clear, understandable, and easy to manage.
  - **Testability:** Structuring code for effective and efficient testing.
  - **Scalability:** Designing components for growth with minimal coupling.
  - **Adaptability:** Allowing easy modifications or adjustments to components in response to changes.

## Integrating AI in Our Study with llamaIndex and Pydantic
Recently, I utilized llamaIndex and Pydantic to develop three Python programs, each illustrating how AI can enhance software design:

1. `poetry run python 1_pattern_design_query.py`
2. `poetry run python 2_rewrite.py`
3. `poetry run python 3_generate_markdown.py`

These programs ask generative AI about the changes in Maintainability, Testability, Scalability, and Adaptability after applying specific design patterns. 

The complete study report is available [here](https://github.com/kevinchwong/design-patterns-for-clean-architecture/blob/main/md/toc.md).

## Unveiling the Coding Process
### 1_pattern_design_query.py
- Begins with identifying common design pattern names using OpenAI.
- Uses Pydantic for structured analysis of each pattern.
- To make sure the text returned is escaped from OpenAI, put "escaped_" as the prefix in the Pydantic class fields. 
- Mermaid scripts offer visual representation in lieu of direct UML diagram generation.
- GPT-3.5 is our primary tool, switching to GPT-4 for more complex analyses.

### 2_rewrite.py
- This phase involves transforming initial insights into a coherent study report.

### 3_generate_markdown.py
- The final step is to compile our findings into well-structured markdown documents.

## Concluding Thoughts
Clean Architecture goes beyond traditional design patterns and principles. It is a holistic approach that fosters resilient, adaptable, and sustainable software systems. Embracing this methodology can lead to significant savings in time and resources and lay the groundwork for a scalable, future-proof architecture.
