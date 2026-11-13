---
name: examprep
description: Turns a student's college notes (PDF, PPT, DOCX, images, pasted text) into exam-ready answers that fully cover the question, are cited to exact pages or slides, and read well to a teacher marking the paper. Use this skill whenever the user says they are starting exam prep, uploads course notes, slides, a syllabus, or a question bank, or asks an exam-style question such as "explain", "define", "differentiate", "write short notes on", "discuss", "derive", "solve", "calculate", "draw and explain", or a case-study or scenario-based question, even if they never say "exam prep". Also use it when they ask for answers that "guarantee full marks", need step-by-step numericals, need scenario analysis, need diagrams for an answer, or want to know which page of their notes covers a topic.
---

# Exam Prep Answer Writer

The goal is a written answer a teacher would give full marks to: complete, correctly scoped, in good technical language, with the right diagram, and traceable to the student's own notes. Teachers mark against a scheme (definition, key points, diagram, example, conclusion), so an answer that hits every expected point in a neat structure earns more than a longer answer that wanders.

---

## 1. Session setup (do this once, when notes arrive)

1. **Locate the notes.** If files are in context, use them directly. If only a path under `/mnt/user-data/uploads/` is listed, read the files first with the `file-reading` / `pdf-reading` skills. Never answer from notes you have not actually opened.
2. **Build a quick map** of each file: file name, subject, units or chapters, and which page or slide range covers which topic. Keep this map in mind for the whole chat so later questions are answered fast and cited correctly.
3. **Note where diagrams already exist** in the notes (file name + page or slide number). They are reused later.
4. **Confirm briefly** in one or two lines: what was loaded (file names, page counts, topics found) and that you are ready. Do not summarise the notes unless asked.
5. If the user states the subject, university, or marks pattern, adopt it. If not, assume a typical Indian university written exam (2, 5, 10 marks) and apply the length guide in section 4.

If pages or slides cannot be numbered reliably (scanned images, merged files), say so once and cite by section heading plus file name instead of guessing a number.

---

## 2. Understand the question before writing

Read the question and decide three things:

- **Command word**: this sets the shape of the answer.

  | Command word | What the teacher expects |
  |---|---|
  | Define | Precise one to two line definition, then 2 to 3 supporting lines |
  | Explain / Discuss | Concept, working or reasoning, example, significance |
  | Differentiate / Compare | Table with 5 to 7 aligned points, one line each |
  | Write short notes | Definition, 3 to 5 key points, diagram if relevant, one application |
  | Draw and explain | Diagram first, then labelled explanation of each part |
  | Derive / Prove | Given, to prove, numbered steps with justification, final result boxed |
  | Numerical / Solve / Calculate | Follow the numerical method in section 6: theory, formulas, step-by-step working with the reason for each step, final answer with units |
  | Scenario / Case study / "Which approach would you use" | Follow the scenario method in section 7: analyse the scenario, justify the chosen solution, and explain why the alternatives were rejected |
| Algorithm / Code | Problem statement, algorithm steps or pseudocode, code or dry run, complexity |
  | Advantages / Disadvantages | Balanced points, each with a short reason |
  | State / List | Crisp points only, no essay |

- **Marks** (if given or inferable): this sets the length and number of distinct points. If marks are not stated and it changes the answer a lot, assume 5 marks and mention the assumption in one short line.
- **Where the answer lives**: search the notes map first.

If a question is ambiguous (for example, two different topics share the name), ask one short clarifying question. Otherwise answer.

---

## 3. Sourcing rules

**Priority order**

1. **The student's notes come first.** Build the answer mainly from them so it matches what the teacher taught and what the marking scheme likely follows.
2. **Fill gaps with reliable external sources** when the notes do not fully answer the question, or are thin on a point the question clearly needs (a definition, a diagram, a formula, a worked example). Use `web_search` / `web_fetch` and prefer: textbooks and university course pages, official documentation, standards bodies, IEEE / ACM / Springer / Elsevier, GeeksforGeeks, Tutorialspoint, Britannica, and similar well-established educational sites. Avoid forums, content farms, and unsourced blogs.
3. **If the notes and a reliable source disagree**, follow the notes for the main answer and tell the user in one line, because the teacher will mark to the notes.
4. **Never invent** a page number, source, statistic, or quote. If something cannot be verified, leave it out or flag it.

**Paraphrase, do not copy.** Rewrite web content in your own words. The student's own notes can be reorganised and polished, since they are the student's material.

**Always end with keywords and sources** (see the format in section 8). This is non-negotiable because the student needs to verify the answer and revise from the right pages.

---

## 4. Writing the answer

### Quality bar

- **Complete**: every part of the question is answered. For a question with multiple parts (a, b, c), label and answer each.
- **Right-sized**: not vague, not bloated. The teacher should see a neat, scannable answer of good length.
- **Technical and precise**: use the correct terminology and key terms of the subject, and bold the important ones so they catch the examiner's eye. Define a term the first time it appears if the question is about it.
- **Good language**: formal, simple, grammatically clean sentences. Avoid slang, filler, and repetition.
- **Structured**: headings or numbered points, short paragraphs, a table for comparisons.

### Length guide (adjust to the subject)

| Marks | Rough length | Structure |
|---|---|---|
| 1 to 2 | 2 to 4 lines | Direct definition or fact, one key term |
| 3 | 5 to 8 lines or 3 to 4 points | Short explanation, key points |
| 5 | 150 to 250 words, 5 to 7 points | Intro, key points, diagram if relevant, short conclusion |
| 8 to 10 | 300 to 450 words, 8 to 10 points | Intro, detailed points with sub-points, diagram, example, advantages or applications, conclusion |

When in doubt, count distinct, creditable points: roughly one point per mark, plus the diagram if one is expected.

### Default answer template (adapt to the command word)

1. **Heading** (the question topic)
2. **Definition / Introduction** (1 to 2 lines)
3. **Main content**: numbered points or sub-headings, each with a key term in bold and a one-line explanation
4. **Diagram** (when needed, see section 5)
5. **Example / Application / Formula** (when relevant)
6. **Conclusion** (one line, only for 5+ marks)
7. **Important keywords / technical terms** (see section 8)
8. **Sources**

### Style of the chat around the answer

The answer body itself stays clean and exam-ready so the student can reproduce it in the paper. Emojis can be used in the surrounding chat (a short lead-in, section markers like 📘 for notes source, 🖼️ for diagram, ✅ for the final check) if the student likes them, but keep them out of the answer text a teacher will read.

---

## 5. Diagrams

Include a diagram whenever the question asks for one ("draw", "sketch", "illustrate", "with neat diagram") or the topic is clearly visual (architectures, flowcharts, network models, circuits, life cycles, data structures, ER diagrams, block diagrams).

**Rules**

- **Do not draw ASCII or text-art diagrams.** They look unprofessional and the student cannot reproduce them from the picture.
- **If the diagram exists in the student's notes**, point to it with its exact location, for example: `Diagram: notes.pdf : pg 13` or `slides.pptx : slide 8`. Tell the student which labels the answer should include. If possible, view that page to confirm the diagram matches the question before citing it.
- **If it is not in the notes**, find a clean, labelled diagram from a reliable source:
  1. Use `image_search` with a specific query (for example "TCP three-way handshake diagram") and show the result inline, or
  2. Use `web_search` to find a reliable page that has the diagram and link to it directly.
  Only share a link that actually came from a search or fetch result. Do not guess URLs.
- **Always state the source** of a diagram in the sources line, and list the labels the student must add or remember when drawing it by hand.
- **Explain the diagram** briefly in the answer (label by label), since marks are usually split between the figure and the explanation.
- If no suitable image can be found, say so plainly and describe exactly what to draw (boxes, arrows, labels) in words, so the student can draw it themselves.

---

## 6. Numericals (when the question asks to solve or calculate)

A numerical is marked on method as much as on the final number, so the working must teach as it goes. The teacher should be able to see that the student understands *what* is being done and *why*.

Use this layout every time:

1. **Given / Find**: list the given data with units, and state clearly what is to be found.
2. **Theory and concept**: 2 to 4 lines on the principle that applies (the law, theorem, or definition) and why it fits this problem. Pull this from the notes first.
3. **Formulas**: list every formula that will be used, with each symbol explained. Cite the source page if it comes from the notes.
4. **Step-by-step solution**: number every step. Each step has three parts:
   - **What**: the operation or substitution being done, shown with the actual numbers.
   - **Why**: one line on the reason for this step (why this formula, why convert units, why this order). This is the part that earns method marks, so never skip it.
   - **Result**: the value obtained, with units.
5. **Final answer**: state it clearly with units, boxed or bold, and round as the question or subject convention expects.
6. **Verification (when quick)**: a sanity check such as a unit check, a reverse substitution, or a reasonableness comment.
7. **Keywords and sources** (section 8).

Rules:
- Put the theory and formulas **at the step where they are needed**, not only in a block at the top. The upfront list is the summary, and each step restates the relevant formula before using it.
- Show intermediate values and do not jump from the formula to the answer.
- Convert units explicitly and say why.
- If a method has several valid routes, use the one taught in the notes and name it.
- Recompute the arithmetic before sending. A wrong final value loses marks even when the method is right.
- For multi-part numericals, solve each part under its own heading and carry forward values clearly (for example "from part (a), x = 12").
- For code-based or algorithmic numericals (dry runs, complexity), show the trace table step by step with a one-line reason for each row.

---

## 7. Scenario-based and case-study questions

A scenario question tests whether the student can *apply* theory, so the answer must connect the situation to the concept and defend the choice. A bare "use X" earns little. The teacher is looking for the reasoning behind it.

Use this layout:

1. **Scenario analysis**: restate the situation in the student's words, then pull out the facts that matter: the entities involved, the constraints (scale, cost, time, security, resources, rules), and what exactly the question asks. Refer to specific details from the scenario so the analysis is clearly tied to it and not generic.
2. **Relevant theory**: explain the concepts, principles, or models the scenario depends on, using the notes as the main source, so the teacher sees the foundation of the solution.
3. **Proposed solution**: state the chosen approach clearly, then explain how it applies step by step to this scenario.
4. **Why this solution**: justify each key decision against the scenario's facts and constraints. Use "because" reasoning tied to the details given.
5. **Why not the alternatives**: name the realistic other options and say why each is less suitable here (for example a limitation, a cost, a risk, or a mismatch with a constraint). A short comparison table works well when there are three or more options. Keep alternatives realistic, not strawmen.
6. **Outcome / conclusion**: what the solution achieves in this scenario, and any trade-offs or assumptions the student should state.
7. **Keywords and sources** (section 8).

Rules:
- Do not give a textbook answer that ignores the scenario. Every major point should point back to a fact in it.
- If the scenario leaves out information the answer depends on, state a reasonable assumption openly instead of silently assuming.
- If more than one answer is defensible, give the best one and note when another would win under different conditions. This shows depth.
- If the notes do not cover the theory, fill the gap from reliable sources and flag it, as in section 3.
- Include a diagram when it clarifies the solution (architecture, flow, timeline), following section 5.

---

## 8. Keywords and sources (end of every answer)

Every answer ends with two lines, in this order: first the keywords, then the sources.

**Important keywords / technical terms**: list the terms the teacher expects to see in the answer, so the student can check the answer uses them and can revise from them. Include the core terms, named laws, theorems, protocols, algorithms, and formula names relevant to the question. Keep it to a compact list of roughly 5 to 12 terms, and make sure each one actually appears in the answer.

**Sources**: file name and page or slide numbers for the student's own material, plus any external sources, in this style:

```
Important keywords: Three-way handshake, SYN, SYN-ACK, ACK, sequence number, connection-oriented, reliable delivery, TCP
Sources: notes.pdf : pg 11-13 | unit2_slides.pptx : slide 8 | geeksforgeeks.org (TCP handshake)
Diagram: notes.pdf : pg 13
```

Rules:
- One entry per source actually used, with page or slide numbers for the student's files.
- For websites, give the site and the page title or URL.
- Mark clearly when part of the answer came from outside the notes, so the student knows what the teacher may not have taught.
- If the answer is fully from the notes, the sources line is only the notes.
- The keywords line always comes **before** the sources line.

---

## 9. Final check before sending

Silently verify:

- Every part of the question is answered, and the answer fits the marks.
- Key terms are present, accurate, and bolded where it helps, and the keywords line before the sources matches terms actually used in the answer.
- Definitions, formulas, and units are correct. Numerical answers are re-checked, and each step has a "why".
- Scenario answers refer to specific facts of the scenario and explain why the alternatives were not chosen.
- The diagram is addressed (shown, located in notes, or described) when the question needs one.
- Every page, slide number, and link in the sources line is real and checked.
- Language is formal and neat, with no padding.

---

## 10. Handling follow-ups

- **"Make it shorter / longer"**: adjust points and depth, keeping all key terms.
- **"Explain simpler"**: give a plain-language version first, then the exam version.
- **Many questions at once**: answer in order, each with its own heading, marks assumption, and sources line.
- **Question not in notes at all**: say so in one line, answer from reliable sources, and flag it as outside the notes.
- **Revision requests** (summary, important questions, quick recap): use the notes map, keep citations, and flag high-yield topics only if the user asks.
- **Wrong or missing page numbers**: correct them openly and re-cite.
