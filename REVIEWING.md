# Reviewing the Japanese edition

*How the translator review of this edition works: what the repository is, who reviews what, how a round runs, the house style, and what to look for.*

## What this repository is

This is the Japanese edition of [Python Programming for Economics and Finance](https://python-programming.quantecon.org/), translated from the English lectures in [QuantEcon/lecture-python-programming](https://github.com/QuantEcon/lecture-python-programming). Every lecture starts as a machine translation by QuantEcon's translation engine, [action-translation](https://github.com/QuantEcon/action-translation), and the edition is built up one lecture at a time: each lecture is drafted, reviewed by one of the edition's two translators on its own pull request, updated from that review and merged. Until a lecture is merged, it is a draft.

The review does two jobs. It makes each lecture right in Japanese, and it teaches the engine: whatever a review corrects goes back into the engine's glossary, rules and lints before the next lecture is drafted, so each draft should need less work than the one before. Every merged lecture is also kept as a reference for measuring later versions of the engine.

Until every lecture is on `main`, changes to the English lectures are not carried across automatically. Once they all are, those changes arrive here as pull requests.

## Who reviews what

The edition has two translators, [@Chihiro2000GitHub](https://github.com/Chihiro2000GitHub) and [@xuanguang-li](https://github.com/xuanguang-li). Each reviews the lectures in one half of the book, divided by part. Every lecture has its own issue in this repository, assigned to its translator: see [@Chihiro2000GitHub's issues](https://github.com/QuantEcon/lecture-python-programming.ja/issues?q=is%3Aissue%20assignee%3AChihiro2000GitHub) and [@xuanguang-li's issues](https://github.com/QuantEcon/lecture-python-programming.ja/issues?q=is%3Aissue%20assignee%3Axuanguang-li). The translators review and suggest; [@mmcky](https://github.com/mmcky) updates each lecture from its review and merges it.

**@Chihiro2000GitHub** reviews the opening page and the parts *Introduction to Python* and *Foundations of Scientific Computing* (13 pages), in this order:

1. `intro.md`: Python Programming for Economics and Finance (a short warm-up, on the pull request that sets up the build)
2. `python_by_example.md`: An Introductory Example
3. `functions.md`: Functions
4. `python_essentials.md`: Python Essentials
5. `oop_intro.md`: OOP I: Objects and Methods
6. `names.md`: Names and Namespaces
7. `python_oop.md`: OOP II: Building Classes
8. `need_for_speed.md`: Python for Scientific Computing
9. `numpy.md`: NumPy
10. `matplotlib.md`: Matplotlib
11. `scipy.md`: SciPy
12. `about_py.md`: About These Lectures
13. `getting_started.md`: Getting Started

**@xuanguang-li** reviews the parts *High Performance Computing*, *Working with Data*, *More Python Programming* and *Other* (14 pages), in this order:

1. `pandas.md`: Pandas
2. `pandas_panel.md`: Pandas for Panel Data
3. `polars.md`: Polars
4. `writing_good_code.md`: Writing Good Code
5. `workspace.md`: Writing Longer Programs
6. `python_advanced_features.md`: More Language Features
7. `debugging.md`: Debugging and Handling Errors
8. `sympy.md`: SymPy
9. `numba.md`: Numba
10. `jax_intro.md`: JAX (with the shared GPU notice, `lectures/_admonition/gpu.md`)
11. `numpy_vs_numba_vs_jax.md`: NumPy vs Numba vs JAX
12. `autodiff.md`: Adventures with Autodiff
13. `troubleshooting.md`: Troubleshooting
14. `status.md`: Execution Statistics

The first full lecture in each half is one that another edition has reviewed or is reviewing, so the results can be compared, and the lectures whose English changes most often come late. The order can still change, for example if a lecture's English is being reworked when its turn comes.

## How a round works

A round is one lecture, and you review one lecture at a time.

1. @mmcky drafts the lecture with the current version of the engine and opens a pull request for it, which closes the lecture's issue when it merges. The description says what is new in the engine since the last round, how the draft was made and machine-checked, and what was left for you to decide, and the pull request links a preview of the rendered page.
2. You read the whole lecture and review it on the pull request. Under **Files changed**, click the blue **+** beside a line (or drag across several lines), add a suggestion, and write the line as you would have it ([GitHub's guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request)). A plain comment is fine for anything a suggestion cannot express, and you can also push commits straight to the branch.
3. When your review is complete, say so on the pull request.
4. @mmcky then reviews your suggestions and updates the lecture and the engine (glossary, rules, lints) before the next lecture is drafted, so the next draft starts from a better place. Suggestions applied to the lecture are committed by script, with you credited as co-author; any not applied are answered on the pull request.
5. @mmcky merges the pull request, and the lecture's issue closes with it.

Terminology questions that affect several lectures are filed as one Decision issue for the round, assigned to both translators, because a term chosen in one half applies to the whole book. The issue outlives the pull request.

GitHub Copilot may leave an automated review on these pull requests. It needs no attention from you.

## House style

**Terms.** The engine follows the Japanese glossary, [`glossary/ja.json`](https://github.com/QuantEcon/action-translation/blob/main/glossary/ja.json) in the engine's repository (live once [QuantEcon/action-translation#69](https://github.com/QuantEcon/action-translation/pull/69) merges), and these rules from its review:

- Japanese only where a standard Japanese term exists; otherwise English, in Latin script. If in doubt, English.
- Personal names stay in Latin script, with no katakana.
- Compound names are joined with ・, never ＝, as in ソロー・スワン成長モデル.
- An abbreviation is spelt out on first use, followed by the abbreviation in parentheses, as in 国内総生産（GDP）; the width of the parentheses is one of the style points below.

**Style.** The first four points below are ruled on [QuantEcon/action-translation#337](https://github.com/QuantEcon/action-translation/issues/337); code comments and figure labels are open questions, to be settled later as an action-translation rule. This table is updated with each ruling:

| Point | House style |
|---|---|
| Register | To be ruled: です・ます調, である調, or です・ます for explanation and である for definitions |
| Sentence punctuation | To be ruled: 、。, ，． or ，。 |
| Parentheses around Latin text and abbreviations | Full-width throughout: 国内総生産（GDP）, 名前空間（namespace）, and asides （…） (ruled 2026-10-02) |
| Spacing between Japanese and Latin words or inline code | A half-width space: NumPy の配列, `x` の値 (ruled 2026-10-02) |
| Code comments | To be ruled: translated into Japanese, or kept in English |
| Figure labels (plot titles, axis labels, legends) | Kept in English for now, until the engine supports a Japanese font (ruled 2026-10-02); a formal rule comes later |

If you think a house-style rule is itself wrong, say so on the pull request: it is then settled once for every lecture that follows, rather than lecture by lecture.

## What matters most

In order:

1. **Meaning errors**: a sentence that says something different from the English, even when it reads fluently. These are the errors only a careful reader catches.
2. **Terms** that are wrong, or that disagree with the glossary or with another lecture.
3. **Register and punctuation** that depart from the house style.
4. **Unnatural Japanese**: wording a good Japanese textbook would not use.
5. **Code comments**, if the draft translates them.

A term that is wrong in one lecture is probably wrong in others. Say so in your comment, and it goes into the glossary once, for every lecture that follows.

## What to skip

- **Errors in the English itself**: see [Errors in the English](#errors-in-the-english) below.
- **The `translation:` block** at the top of each file, which holds the title and the heading map the engine uses to match sections across languages. If you change a heading, @mmcky updates its line in the block when applying your suggestion.
- **Code, program output and screenshots**, which are left as they are. Code comments, figure labels and other text inside code need your eye only where the draft translates them.
- **Structure**: the number and order of headings, code cells and directives are machine-checked against the English before each pull request opens, so only their text needs your eye.

## Time

There is no deadline. You review one lecture at a time, and what each round teaches goes into the engine before the next lecture is drafted. If you note on the pull request roughly how long the review took, it helps us plan, but that is optional.

## AI tools

If an AI tool helped with a suggestion, commit or comment on a pull request, add an `Assisted-by: TOOL (MODEL)` line to it, as QuantEcon's Code of AI Use, [QEP-5](https://github.com/QuantEcon/qeps/blob/main/qeps/qep-0005-code-of-ai-use.md), asks.

## Errors in the English

A careful review often finds mistakes in the English lectures themselves. Those are corrected upstream, in [QuantEcon/lecture-python-programming](https://github.com/QuantEcon/lecture-python-programming/issues), so that every edition benefits. A short issue there is plenty, or mention the problem on the round's pull request and @mmcky will raise it.
