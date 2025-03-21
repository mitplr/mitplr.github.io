---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
---

![MIT Programming Languages Review logo](mitplr2025.png){: width="90%" }

# MIT Programming Languages Review Workshop

[Registration](https://mit.co1.qualtrics.com/jfe/form/SV_3aR7xGFs4fYigg6) is now open for the annual MIT PLR Workshop 2025!
Join us in-person or virtually a fresh lineup of talks from authors of potentially high-impact, significant works published in recent years at venues!
This year's selected papers are listed below.
We will be holding the PL Review on April 24th, 2025 at MIT building 34 (50 Vassar St, Cambridge, MA) in the Grier Room (34-401).

The mission of the MIT PL Review is to highlight recent developments that we believe have significant potential to shape the future direction of PL research and/or industry practice. We aim to select papers that may substantially transform the PL community and beyond, with a focus on emerging trends rather than established lines of research. We favor papers whose contributions are broadly accessible (and likely to be appreciated) across the PL community, but we do not limit the papers to those published at PL venues. Our selection process is not meant to provide an objective evaluation of works but rather to highlight and celebrate works that resonated with our committee members.

# Selected Papers<sup>\*</sup>
<sup>\*</sup>*To avoid conflicts of interest, no MIT affiliated papers were considered.*

## Outcome Logic: A Unifying Foundation for Correctness and Incorrectness Reasoning

### Authors: Noam Zilberstein, Derek Dreyer, Alexandra Silva

Program logics for bug-finding (such as the recently introduced Incorrectness Logic) have framed correctness and incorrectness as dual concepts requiring different logical foundations. In this paper, we argue that a single unified theory can be used for both correctness and incorrectness reasoning. We present Outcome Logic (OL), a novel generalization of Hoare Logic that is both monadic (to capture computational effects) and monoidal (to reason about outcomes and reachability). OL expresses true positive bugs, while retaining correctness reasoning abilities as well. To formalize the applicability of OL to both correctness and incorrectness, we prove that any false OL specification can be disproven in OL itself. We also use our framework to reason about new types of incorrectness in nondeterministic and probabilistic programs. Given these advances, we advocate for OL as a new foundational theory of correctness and incorrectness.

Notes from the program committee:

> This work unifies standard Hoare logic and Incorrectness logic, producing a subsuming paradigm that also gains additional expressivity thanks to the interactions between the two subsystems. We believe that there is significant demand for true-positive bug finding tools like incorrectness logic, and that the synergistic combination of both styles of reasoning will aid in the adoption of verification in critical production code. Specifically, we see the potential to introduce analyses in industry for the purpose of bug-finding and then build gradually and selectively toward component-wise verification.

Read the paper [here](https://dl.acm.org/doi/10.1145/3586045)

## MiniMalloc: A Lightweight Memory Allocator for Hardware-Accelerated Machine Learning

### Authors: Michael D. Moffitt

We present a new approach to static memory allocation, a key problem that arises in the compilation of machine learning models onto the resources of a specialized hardware accelerator. Our methodology involves a recursive depth-first search that limits exploration to a special class of canonical solutions, dramatically reducing the size of the search space. We also develop a spatial inference technique that exploits this special structure by pruning unpromising partial assignments and backtracking more effectively than otherwise possible. Finally, we introduce a new mechanism capable of detecting and eliminating dominated solutions from consideration. Empirical results demonstrate orders of magnitude improvement in performance as compared to the previous state-of-the-art on many benchmarks, as well as a substantial reduction in library size.

Notes from the program committee:

> This paper introduces a lattice-based canonical form for static memory allocation, leveraging offset and index monotonicity concepts to dramatically prune the search space. This enables their static memory allocator, minimalloc, to be orders of magnitude faster than the state of the art. Their lattice representation may provide a useful framework for a range of combinatorial optimization problems.

Read the paper [here](https://dl.acm.org/doi/10.1145/3623278.3624752)

## Knowledge Transfer from High-Resource to Low-Resource Programming Languages for Code LLMs

### Authors: Federico Cassano, John Gouwar, Francesca Lucchetti, Claire Schlesinger, Anders Freeman, Carolyn Jane Anderson, Molly Q Feldman, Michael Greenberg, Abhinav Jangda, Arjun Guha

Over the past few years, Large Language Models of Code (Code LLMs) have started to have a significant impact on programming practice. Code LLMs are also emerging as building blocks for research in programming languages and software engineering. However, the quality of code produced by a Code LLM varies significantly by programming language. Code LLMs produce impressive results on high-resource programming languages that are well represented in their training data (e.g., Java, Python, or JavaScript), but struggle with low-resource languages that have limited training data available (e.g., OCaml, Racket, and several others). This paper presents an effective approach for boosting the performance of Code LLMs on low-resource languages using semi-synthetic data. Our approach, called MultiPL-T, generates high-quality datasets for low-resource languages, which can then be used to fine-tune any pretrained Code LLM. MultiPL-T translates training data from high-resource languages into training data for low-resource languages in the following way. 1) We use a Code LLM to synthesize unit tests for commented code from a high-resource source language, filtering out faulty tests and code with low test coverage. 2) We use a Code LLM to translate the code from the high-resource source language to a target low-resource language. This gives us a corpus of candidate training data in the target language, but many of these translations are wrong. 3) We use a lightweight compiler to compile the test cases generated in (1) from the source language to the target language, which allows us to filter our obviously wrong translations. The result is a training corpus in the target low-resource language where all items have been validated with test cases. We apply this approach to generate tens of thousands of new, validated training items for five low-resource languages: Julia, Lua, OCaml, R, and Racket, using Python as the source high-resource language. Furthermore, we use an open Code LLM (StarCoderBase) with open training data (The Stack), which allows us to decontaminate benchmarks, train models without violating licenses, and run experiments that could not otherwise be done. Using datasets generated with MultiPL-T, we present fine-tuned versions of StarCoderBase and Code Llama for Julia, Lua, OCaml, R, and Racket that outperform other fine-tunes of these base models on the natural language to code task. We also present Racket fine-tunes for two very recent models, DeepSeek Coder and StarCoder2, to show that MultiPL-T continues to outperform other fine-tuning approaches for low-resource languages. The MultiPL-T approach is easy to apply to new languages, and is significantly more efficient and effective than alternatives such as training longer.

Notes from the program committee:

> This work orchestrates language models and PL techniques to bootstrap high-quality data for programming languages that are underrepresented in Internet-scale code datasets, improving, for example, the performance of AI code assistants on these languages. A bottleneck of modern AI systems is high-quality data, so developing techniques to generate synthetic data will become increasingly valuable. The authors' system is judicious in the choice of steps that make use of reliable, non-neural components and serves as a template for future work in semi-synthetic data generation.

Read the paper [here](https://dl.acm.org/doi/10.1145/3689735)

## A Two-Phase Infinite/Finite Low-Level Memory Model

### Authors: Calvin Beck, Irene Yoon, Hanxi Chen, Yannick Zakowski, Steve Zdancewic

This paper provides a novel approach to reconciling complex low-level memory model features, such as pointer--integer casts, with desired refinements that are needed to justify the correctness of program transformations. The idea is to use a "two-phase" memory model, one with an unbounded memory and corresponding unbounded integer type, and one with a finite memory; the connection between the two levels is made explicit by a notion of refinement that handles out-of-memory behaviors. This approach allows for more optimizations to be performed and establishes a clear boundary between the idealized semantics of a program and the implementation of that program on finite hardware. The two-phase memory model has been incorporated into an LLVM IR semantics, demonstrating its utility in practice in the context of a low-level language with features like undef and bitcast. This yields infinite and finite memory versions of the language semantics that are proven to be in refinement with respect to out-of-memory behaviors. Each semantics is accompanied by a verified executable reference interpreter. The semantics justify optimizations, such as dead-alloca-elimination, that were previously impossible or difficult to prove correct.

Notes from the program committee:

> The impedence mismatch between theoretically-infinite high-level languages and finite computer architechtures presents a constent difficulty in the development of correct compiler pipelines, especially verified ones. This paper presents a methodology and a convincing case study that demonstrates how to decouple the vast majority of compilation reasoning from the finite target setting. We expect that, going forward, any compilation pipelines that do not track and enforce strict bounds on memory usage should follow the template set out in this work.

Read the paper [here](https://dl.acm.org/doi/10.1145/3674652)

## PyTorch 2: Faster Machine Learning Through Dynamic Python Bytecode Transformation and Graph Compilation

### Authors: Jason Ansel, Edward Yang, Horace He, Natalia Gimelshein, Animesh Jain, Michael Voznesenksy, Bin Bao, Peter Bell, David Berard, Evgeni Burovski, Geeta Chauhan, Anjali Chourdia, Will Constable, Alban Desmaison, Zachary DeVito, Elias Ellison, Will Feng, Jiong Gong, Michael Gschwind, Brian Hirsh, Sherlock Huang, Kshiteej Kalambarkar, Laurent Kirsch, Michael Lazos, Mario Lezcano, Yanbo Liang, Jason Liang, Yinghai Lu, CK Luk, Bert Maher, Yunjie Pan, Christian Puhrsch, Matthias Reso, Mark Saroufim, Marcos Yukio Siraichi, Helen Suk, Michael Suo, Phil Tillet, Eikan Wang, Xiaodon Wang, William Wen, Shunting Zhang, Xu Zhao, Keren Zhou, Richard Zou, Ajit Matthews, Gregory Chanan, Peng Wu, Soumith Chintala

This paper introduces two extensions to the popular PyTorch machine learning framework, TorchDynamo and TorchInductor, which implement the torch.compile feature released in PyTorch 2. TorchDynamo is a Python-level just-in-time (JIT) compiler that enables graph compilation in PyTorch programs without sacrificing the flexibility of Python. It achieves this by dynamically modifying Python bytecode before execution and extracting sequences of PyTorch operations into an FX graph, which is then JIT compiled using one of many extensible backends. TorchInductor is the default compiler backend for TorchDynamo, which translates PyTorch programs into OpenAI's Triton for GPUs and C++ for CPUs. Results show that TorchDynamo is able to capture graphs more robustly than prior approaches while adding minimal overhead, and TorchInductor is able to provide a 2.27× inference and 1.41× training geometric mean speedup on an NVIDIA A100 GPU across 180+ real-world models, which outperforms six other compilers. These extensions provide a new way to apply optimizations through compilers in eager mode frameworks like PyTorch.

Notes from the program committee:

> This work introduces TorchDynamo and TorchInductor, enabling graph compilation while preserving PyTorch’s eager execution model. The authors navigated complex trade-offs in language design, compilation strategies, and runtime performance to deliver a system that provides automatic speedups to real-world ML workloads while maintaining the expressiveness of dynamic Python. We believe that this work advances a compiler design in ML systems, making high-performance execution more accessible.

Read the paper [here](https://dl.acm.org/doi/10.1145/3620665.3640366)

## Scallop: A Language for Neurosymbolic Programming

### Authors: Ziyang Li, Jiani Huang, Mayur Naik

We present Scallop, a language which combines the benefits of deep learning and logical reasoning. Scallop enables users to write a wide range of neurosymbolic applications and train them in a data- and compute-efficient manner. It achieves these goals through three key features: 1) a flexible symbolic representation that is based on the relational data model; 2) a declarative logic programming language that is based on Datalog and supports recursion, aggregation, and negation; and 3) a framework for automatic and efficient differentiable reasoning that is based on the theory of provenance semirings. We evaluate Scallop on a suite of eight neurosymbolic applications from the literature. Our evaluation demonstrates that Scallop is capable of expressing algorithmic reasoning in diverse and challenging AI tasks, provides a succinct interface for machine learning programmers to integrate logical domain knowledge, and yields solutions that are comparable or superior to state-of-the-art models in terms of accuracy. Furthermore, Scallop's solutions outperform these models in aspects such as runtime and data efficiency, interpretability, and generalizability.

Notes from the program committee:

> Neural networks often find it hard to incorporate discrete/logical reasoning, and this reasoning is often well understood. Scallop is one approach to fixing this problem, by having a neural network output belief values that are then processed via a datalog logic programming system into the output predictions. This pipeline can be backpropagated through for end-to-end training. 

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3591280)

## Lilac: A Modal Separation Logic for Conditional Probability

### Authors: John M. Li, Amal Ahmed, Steven Holtzen

We present Lilac, a separation logic for reasoning about probabilistic programs where separating conjunction captures probabilistic independence. Inspired by an analogy with mutable state where sampling corresponds to dynamic allocation, we show how probability spaces over a fixed, ambient sample space appear to be the natural analogue of heap fragments, and present a new combining operation on them such that probability spaces behave like heaps and measurability of random variables behaves like ownership. This combining operation forms the basis for our model of separation, and produces a logic with many pleasant properties. In particular, Lilac has a frame rule identical to the ordinary one, and naturally accommodates advanced features like continuous random variables and reasoning about quantitative properties of programs. Then we propose a new modality based on disintegration theory for reasoning about conditional probability. We show how the resulting modal logic validates examples from prior work, and give a formal verification of an intricate weighted sampling algorithm whose correctness depends crucially on conditional independence structure.

Notes from the program committee:

> This paper presents a separation logic for probabilistic programs, in which (as in several pioneering papers on probabilistic separation logic) separation is interpreted as probabilistic independence. The key innovations here are (1) a new modality for reasoning about conditional independence, and (2) a new and non-trivial insight about the right way to instantiate the analogy between heap disjointness and independence. In particular, the paper proposes that the right analogy for a heap is a probability space; the right analogy for heap extension is refinement of the probability space's sigma-algebra; the right analogy for ownership is measurability with respect to the probability space; and the right analogy for the disjoint union of heaps is the independent combination of probability spaces. Setting things up in this way leads to clean proof rules, including a direct analogue of the usual frame rule. Lilac has already influenced newer work on probabilistic program logics, and we expect many future efforts to reason formally about probabilistic programs will benefit from its insights.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3591226)

## Verus: Verifying Rust Programs using Linear Ghost Types

### Authors: Andrea Lattuada, Travis Hance, Chanhee Cho, Matthias Brun, Isitha Subasinghe, Yi Zhou, Jon Howell, Bryan Parno, Chris Hawblitzel

The Rust programming language provides a powerful type system that checks linearity and borrowing, allowing code to safely manipulate memory without garbage collection and making Rust ideal for developing low-level, high-assurance systems. For such systems, formal verification can be useful to prove functional correctness properties beyond type safety. This paper presents Verus, an SMT-based tool for formally verifying Rust programs. With Verus, programmers express proofs and specifications using the Rust language, allowing proofs to take advantage of Rust's linear types and borrow checking. We show how this allows proofs to manipulate linearly typed permissions that let Rust code safely manipulate memory, pointers, and concurrent resources. Verus organizes proofs and specifications using a novel mode system that distinguishes specifications, which are not checked for linearity and borrowing, from executable code and proofs, which are checked for linearity and borrowing. We formalize Verus' linearity, borrowing, and modes in a small lambda calculus, for which we prove type safety and termination of specifications and proofs. We demonstrate Verus on a series of examples, including pointer-manipulating code (an xor-based doubly linked list), code with interior mutability, and concurrent code.

Notes from the program committee:

> This work demonstrates the viability of linear types and borrowing in practical, automated systems verification at scale. Specifically, it shows that they synergize with the style of interactive theorem prover currently best-represented by Dafny, improving both tool performance and ease of reasoning. We expect verification efforts based on Verus or similar systems to benefit from these advantages as compared to Dafny developments and it has already had a positive impact on several research systems.

Read the paper [here](https://dl.acm.org/doi/10.1145/3586037)

You can see last year's program [here](plr2024.md).

# PL Review Program Committee

- Manya Bansal
- Teodoro Collin (Program Chair)
- Kavi Gupta
- Yuka Ikarashi
- Dustin Jamner
- Derek Leung
- Alex Lew
- Amanda Liu (Conference Chair)
- Logan Weber
- Jaeyeon Won
