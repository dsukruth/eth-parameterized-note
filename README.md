# Subexponential parameterized algorithms from the claimed refutation of ETH

**Dhanush P Sukruth** · November 1, 2026

**[paper.pdf](paper.pdf)** · LaTeX source: [paper.tex](paper.tex) · Explainer with diagrams: [blog post](blog/README.md)

## Summary

OpenAI and Anthropic have each claimed a deterministic algorithm that counts the satisfying assignments of a bounded-width CNF formula in subexponential time. If correct, this refutes the Exponential Time Hypothesis (ETH). This note takes that counting theorem as a black box. It turns several ETH-based 2^o(k) lower bounds from parameterized complexity into explicit algorithms, where k is the solution size:

| Problem | Running time |
|---|---|
| Vertex Cover | 2^O(k log log k / √log k) + poly(n) |
| Max-Cut | 2^O(k / √log k) + poly(n) |
| Max-c-SAT (fixed c) | 2^O(k / √log k) + poly(n) |
| Independent Set, Vertex Cover, Dominating Set on graphs of max degree Δ | 2^O_Δ(k / √log k) + poly(n) |
| Counting dominating sets of size ≤ k, max degree Δ | 2^O_Δ(k / √log k) + poly(n) |

All algorithms are deterministic and find a solution when one exists. Each one shrinks the instance to O(k) size, encodes it as a count-preserving CNF formula with O(k) variables, and calls the counting algorithm.

## Scope

- **Conditional.** Every result depends on the claimed counting theorem ([OpenAI, Thm 1.1](https://github.com/openai/math/blob/main/preprints/The-Exponential-Time-Hypothesis-is-False-October-25-2026/paper.pdf); [Anthropic, Thm 1](https://github.com/anthropics/formal-math/tree/main/eth)). That theorem has not yet been independently verified.
- **Novelty.** For most of these problems, the existence of 2^o(k) algorithms already follows from an equivalence of Cai and Juedes (JCSS 2003) or from Corollary 7 of Anthropic's paper. This note contributes the explicit rates and short self-contained proofs.
- **Practicality.** The bounds are purely asymptotic and have no practical significance.

## AI assistance

The results were identified, and the proofs and text drafted, with the assistance of Claude (Anthropic), an AI model. The author takes responsibility for the content.

## Building

```sh
pdflatex paper.tex && pdflatex paper.tex
```

Comments and corrections are welcome. Please open an issue.
