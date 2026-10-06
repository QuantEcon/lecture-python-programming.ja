# Reviewing the Japanese edition

*How the translator review of this edition works. The process is in the QuantEcon Translation Manual; this file keeps what belongs to this edition: who reviews which lectures, and in what order.*

## The manual

The [QuantEcon Translation Manual](https://quantecon.github.io/project-translation/) sets out how a review works, for every edition. Read these pages before your first lecture:

- [How a review round works](https://quantecon.github.io/project-translation/review-round.html)
- [Reviewing on GitHub](https://quantecon.github.io/project-translation/reviewing-on-github.html): suggestions, or a commit for a larger change
- [What to look for](https://quantecon.github.io/project-translation/what-to-look-for.html)
- [Review by hand](https://quantecon.github.io/project-translation/review-by-hand.html)

The manual's [Japanese page](https://quantecon.github.io/project-translation/languages/ja.html) has this edition's term policy, house style, settled terms, open questions and rulings log. It is updated with each ruling.

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

## A round, in brief

A round is one lecture, and you review one lecture at a time. The manual's [How a review round works](https://quantecon.github.io/project-translation/review-round.html) has the details.

1. @mmcky drafts the lecture with the current version of the engine and opens a pull request for it. The pull request links a preview of the rendered page, and closes the lecture's issue when it merges.
2. You read the whole lecture and review it on the pull request: a suggestion on any line you would change, or a commit to the branch for a larger change. Use a plain comment for anything a suggestion cannot express.
3. When your review is complete, approve the pull request and mention @mmcky in the summary, for example: "Review complete. @mmcky, this is ready to merge."
4. @mmcky applies your suggestions, with you credited as co-author, and answers any that are not applied on the pull request. The engine (glossary, rules, lints) is updated before the next lecture is drafted.
5. @mmcky merges the pull request, and the lecture's issue closes with it.

Terminology questions that affect several lectures go to one Decision issue for the round, assigned to both translators, because a term chosen in one half applies to the whole book. The issue outlives the pull request.

GitHub Copilot may leave an automated review on these pull requests. It needs no attention from you.

## Policies in brief

- **Review by hand.** Read and verify every edit yourself. Dictionaries and spelling and grammar checkers are fine when you check each change, but do not let AI or machine translation write or translate your edits. See [Review by hand](https://quantecon.github.io/project-translation/review-by-hand.html).
- **Errors in the English go upstream.** Open an issue in [QuantEcon/lecture-python-programming](https://github.com/QuantEcon/lecture-python-programming/issues), then link it on the translated line. Your review goes ahead without waiting for the fix. You may use AI tools to help write that issue. See [Errors in the English](https://quantecon.github.io/project-translation/errors-in-the-english.html).
- **Merging.** Write access includes the right to merge. Leave merging to @mmcky: each merge goes with an update to the engine.

## Time

There is no deadline. If you note on the pull request roughly how long the review took, it helps us plan, but that is optional.
