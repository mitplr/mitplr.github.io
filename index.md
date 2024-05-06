---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
---

![MIT Programming Languages Review logo](mitplr2024.png){: width="90%" }

# MIT Programming Languages Review

The mission of the MIT PL Review is to highlight recent developments that we believe have significant potential to shape the future direction of PL research and/or industry practice. We aim to select papers that may substantially transform the PL community and beyond, with a focus on emerging trends rather than established lines of research. We favor papers whose contributions are broadly accessible (and likely to be appreciated) across the PL community, but we do not limit the papers to those published at PL venues. Our selection process is not meant to provide an objective evaluation of works but rather to highlight and celebrate works that resonated with our committee members.

Thank you for coming! We look forward to seeing you next year!
Recordings of the presentations and faculty panel are now available [here](https://www.youtube.com/watch?v=tPo2Nx36hnw&list=PL_Rqr4dnpWeIAWgEkiTqLbUJ5DT21rcbu&pp=gAQBiAQB)!
You can see last year's program [here](plr2023.md).

# Schedule

Time | Event
---|---
9:00-10:00 | Breakfast |
10:00-10:30 | [Prompting Is Programming: A Query Language for Large Language Models](https://youtu.be/tPo2Nx36hnw?si=IwZILyk0IT9g-Uh2)
10:30-11:00 | [Bit-Stealing Made Legal](https://youtu.be/x2l7hdUGN58?si=fg7ncuaaDFYt2a2W)
11:00-11:30 | [Efficient Bottom-Up Synthesis for Programs with Local Variables](https://youtu.be/plBSa83AVsM?si=VDzP9qblNF61AzWi)
11:30-12:30 | Lunch
12:30-1:00 | [Guided Equality Saturation](https://youtu.be/yCb1-Nq1fNk)
1:00-1:30 | [Algebraic Effects Meet Hoare Logic in Cubical Agda](https://youtu.be/wXzH9AM5PxQ?si=G4_YLcrCm5R2PUIZ)
1:30-2:00 | [An Extensible User Interface for Lean 4](https://youtu.be/qH4tBAXbmXE?si=SA-TiGTz9ZuAB81z)
2:00-2:30 | Coffee Break
2:30-3:00 | [Register Tiling for Unstructured Sparsity in Neural Network Inference](https://youtu.be/n-9Yk-16qwU?si=4eVSpmV4bQzhwWLK)
3:00-3:30 | [Better Together: Unifying Datalog and Equality Saturation](https://youtu.be/PFdsmWQw2nM?si=8K7egTcAmRNQGJHE)
3:30-4:00 | [Instruction Scheduling for the GPU on the GPU](https://youtu.be/o0Lc-ApzyVc?si=2Z_R2kg_ixQnMe9k)
4:00-5:00 | [PL Faculty Panel](https://youtu.be/ednSCb-RpIU?si=8SjX5aJc7MONH1T7)

# Selected Papers<sup>\*</sup>
<sup>\*</sup>*To avoid conflicts of interest, no MIT affiliated papers were considered.*

## Better Together: Unifying Datalog and Equality Saturation

### Authors: Yihong Zhang, Yisu Remy Wang, Oliver Flatt, David Cao, Philip Zucker, Eli Rosenthal, Zachary Tatlock, Max Willsey

### [Presentation available](https://youtu.be/PFdsmWQw2nM?si=8K7egTcAmRNQGJHE)

We present egglog, a fixpoint reasoning system that unifies Datalog and equality saturation (EqSat). Like Datalog, it supports efficient incremental execution, cooperating analyses, and lattice-based reasoning. Like EqSat, it supports term rewriting, efficient congruence closure, and extraction of optimized terms.
We identify two recent applications--a unification-based pointer analysis in Datalog and an EqSat-based floating-point term rewriter--that have been hampered by features missing from Datalog but found in EqSat or vice-versa. We evaluate egglog by reimplementing those projects in egglog. The resulting systems in egglog are faster, simpler, and fix bugs found in the original systems.

Notes from the program committee:

> By unifying datalog and eqsat, this work neatly combines two long standing lines of work in PL: datalog based analysis and eqSat based analysis. We think that in doing so this work will become a major point of exchange between these two communities in addition to non-trivially improving the existing PL applications of egraphs. 

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3591239)

## Prompting Is Programming: A Query Language for Large Language Models

### Authors: Luca Beurer-Kellner, Marc Fischer, Martin Vechev

### [Presentation available](https://youtu.be/tPo2Nx36hnw?si=IwZILyk0IT9g-Uh2)

Large language models have demonstrated outstanding performance on a wide range of tasks such as question answering and code generation. On a high level, given an input, a language model can be used to automatically complete the sequence in a statistically-likely way. Based on this, users prompt these models with language instructions or examples, to implement a variety of downstream tasks. Advanced prompting methods can even imply interaction between the language model, a user, and external tools such as calculators. However, to obtain state-of-the-art performance or adapt language models for specific tasks, complex task- and model-specific programs have to be implemented, which may still require ad-hoc interaction.
Based on this, we present the novel idea of Language Model Programming (LMP). LMP generalizes language model prompting from pure text prompts to an intuitive combination of text prompting and scripting. Additionally, LMP allows constraints to be specified over the language model output. This enables easy adaption to many tasks while abstracting language model internals and providing high-level semantics.
To enable LMP, we implement LMQL (short for Language Model Query Language), which leverages the constraints and control flow from an LMP prompt to generate an efficient inference procedure that minimizes the number of expensive calls to the underlying language model.
We show that LMQL can capture a wide range of state-of-the-art prompting methods in an intuitive way, especially facilitating interactive flows that are challenging to implement with existing high-level APIs. Our evaluation shows that we retain or increase the accuracy on several downstream tasks, while also significantly reducing the required amount of computation or cost in the case of pay-to-use APIs (26-85% cost savings).
  
Notes from the program committee:

> The probabilistic nature of large language models makes them unreliable for many tasks, hindering the realization of their full potential. Constrained generation is a promising avenue to improve their reliability, and this work is the first to both systematize constrained generation for large language models and put forth a programming model that facilitates it. Taken to its limit, this work enables confident integration of LLMs into software systems.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3591300)
  
## Instruction Scheduling for the GPU on the GPU

### Authors: Ghassan Shobaki, Pınar Muyan-Özçelik, Josh Hutton, Bruce Linck, Vladislav Malyshenko, Austin Kerbow, Ronaldo Ramirez-Ortega, Vahl Scott Gordon

### [Presentation available](https://youtu.be/o0Lc-ApzyVc?si=2Z_R2kg_ixQnMe9k)

In this paper, we show how to use the GPU to parallelize a precise instruction scheduling algorithm that is based on Ant Colony Optimization (ACO). ACO is a nature-inspired intelligent-search technique that has been used to compute precise solutions to NP-hard problems in operations research (OR). Such intelligent-search techniques were not used in the past to solve NP-hard compiler optimization problems, because they require substantially more computation than the heuristic techniques used in production compilers. In this work, we show that parallelizing such a compute-intensive technique on the GPU makes using it in compilation reasonably practical. The register-pressure-aware instruction scheduling problem addressed in this work is a multi-objective optimization problem that is significantly more complex than the problems that were previously solved using parallel ACO on the GPU. We describe a number of techniques that we have developed to efficiently parallelize an ACO algorithm for solving this multi-objective optimization problem on the GPU. The target processor is also a GPU. Our experimental evaluation shows that parallel ACO-based scheduling on the GPU runs up to 27 times faster than sequential ACO-based scheduling on the CPU, and this leads to reducing the total compile time of the rocPRIM benchmarks by 21%. ACO-based scheduling improves the execution-speed of the compiled benchmarks by up to 74% relative to AMD's production scheduler. To the best of our knowledge, our work is the first successful attempt to parallelize a compiler optimization algorithm on the GPU.
  
Notes from the program committee:

> This work introduces a technique for parallelizing a precise instruction scheduling algorithm on the GPU based in intelligent-search techniques. We believe that going forward, works that make compute-intensive compiler techniques feasible like this, will be developed and continue to meaningfully expand the menu of compiler optimization techniques used and available.

Read the paper [here](https://www.computer.org/csdl/proceedings-article/cgo/2024/10444869/1UUdPbvL0Uo)

## Guided Equality Saturation

### Authors: Thomas Koehler, Andrés Goens, Siddharth Bhat, Tobias Grosser, Phil Trinder, Michel Steuwer

### [Presentation available](https://youtu.be/yCb1-Nq1fNk)

Rewriting is a principled term transformation technique with uses across theorem proving and compilation. In theorem proving, each rewrite is a proof step; in compilation, rewrites optimize a program term. While developing rewrite sequences manually is possible, this process does not scale to larger rewrite sequences. Automated rewriting techniques, like greedy simplification or equality saturation, work well without requiring human input. Yet, they do not scale to large search spaces, limiting the complexity of tasks where automated rewriting is effective, and meaning that just a small increase in term size or rewrite length may result in failure. This paper proposes a semi-automatic rewriting technique as a means to scale rewriting by allowing human insight at key decision points. Specifically, we propose guided equality saturation that embraces human guidance when fully automated equality saturation does not scale. The rewriting is split into two simpler automatic equality saturation steps: from the original term to a human-provided intermediate guide, and from the guide to the target. Complex rewriting tasks may require multiple guides, resulting in a sequence of equality saturation steps. A guide can be a complete term, or a sketch containing undefined elements that are instantiated by the equality saturation search. Such sketches may be far more concise than complete terms. We demonstrate the generality and effectiveness of guided equality saturation using two case studies. First, we integrate guided equality saturation in the Lean 4 proof assistant. Proofs are written in the style of textbook proof sketches, as a series of calculations omitting details and skipping steps. These proofs conclude in less than a second instead of minutes when compared to unguided equality saturation, and can find complex proofs that previously had to be done manually. Second, in the compiler of the Rise array language, where unguided equality saturation fails to perform optimizations within an hour and using 60 GB of memory, guided equality saturation performs the same optimizations with at most 3 guides, within seconds using less than 1 GB memory.

Notes from the program committee:

> This paper introduces guided equality saturation, a semi-automatic rewriting technique that enables equality saturation to scale by allowing human insight to guide the process at key points. The authors demonstrate its effectiveness through case studies in theorem proving and program optimization, presenting a promising direction for future research that combines human intuition with the power of automation.

Read the paper [here](https://dl.acm.org/doi/10.1145/3632900)

## An Extensible User Interface for Lean 4

### Authors: Wojciech Nawrocki, Edward W. Ayers, Gabriel Ebner

### [Presentation available](https://youtu.be/qH4tBAXbmXE?si=SA-TiGTz9)

Contemporary proof assistants rely on complex automation and process libraries with millions of lines of code. At these scales, understanding the emergent interactions between components can be a serious challenge. One way of managing complexity, long established in informal practice, is through varying external representations. For instance, algebraic notation facilitates term-based reasoning whereas geometric diagrams invoke spatial intuition. Objects viewed one way become much simpler than when viewed differently. In contrast, modern general-purpose ITP systems usually only support limited, textual representations. Treating this as a problem of human-computer interaction, we aim to demonstrate that presentations - UI elements that store references to the objects they are displaying - are a fruitful way of thinking about ITP interface design. They allow us to make headway on two fronts - introspection of prover internals and support for diagrammatic reasoning. To this end we have built an extensible user interface for the Lean 4 prover with an associated ProofWidgets 4 library of presentation-based UI components. We demonstrate the system with several examples including type information popups, structured traces, contextual suggestions, a display for algebraic reasoning, and visualizations of red-black trees. Our interface is already part of the core Lean distribution.

Notes from the program committee:

> This paper illustrates an important design space in the development of interactive theorem provers: interactive visual components. Especially as mathematicians begin formalizing more of their work, frameworks that allow users to percieve, interact with, and express their proofs visually may become a critical feature in improving the ITP experience to or beyond the level of paper proofs.

Read the paper [here](https://drops.dagstuhl.de/entities/document/10.4230/LIPIcs.ITP.2023.24)

## Register Tiling for Unstructured Sparsity in Neural Network Inference

### Authors: Lucas Wilkinson, Kazem Cheshmi, Maryam Mehri Dehnavi

### [Presentation available](https://youtu.be/n-9Yk-16qwU?si=4eVSpmV4bQzhwWLK)

Unstructured sparse neural networks are an important class of machine learning (ML) models, as they compact model size and reduce floating point operations. The execution time of these models is frequently dominated by the sparse matrix multiplication (SpMM) kernel, C=A× B, where A is a sparse matrix, and B and C are dense matrices. The unstructured sparsity pattern of matrices in pruned machine learning models along with their sparsity ratio has rendered useless the large class of libraries and systems that optimize sparse matrix multiplications. Reusing registers is particularly difficult because accesses to memory locations should be known statically. This paper proposes Sparse Register Tiling, a new technique composed of an unroll-and-sparse-jam transformation followed by data compression that is specifically tailored to sparsity patterns in ML matrices. Unroll-and-sparse-jam uses sparsity information to jam the code while improving register reuse. Sparse register tiling is evaluated across 2396 weight matrices from transformer and convolutional models with a sparsity range of 60-95% and provides an average speedup of 1.72× and 2.65× over MKL SpMM and dense matrix multiplication, respectively, on a multicore CPU processor. It also provides an end-to-end speedup of 2.12× for MobileNetV1 with 70% sparsity on an ARM processor commonly used in edge devices.

Notes from the program committee:

> This paper presents an innovative technique designed to improve hardware utilization for sparse programs. The authors illustrate how this method boosts performance by creating specialized code that maximizes register reuse, customized to fit the sparsity pattern. Looking ahead, we believe this approach holds broad applicability beyond SpMM on CPU, potentially accelerating various sparse applications in the future.

Read the paper [here](https://dl.acm.org/doi/pdf/10.1145/3591302)

## Bit-Stealing Made Legal

### Authors: Thaïs Baudon, Gabriel Radanne, Laure Gonnord

### [Presentation available](https://youtu.be/x2l7hdUGN58?si=fg7ncuaaDFYt2a2W)

Initially present only in functional languages such as OCaml and Haskell, Algebraic Data Types (ADTs) have now become pervasive in mainstream languages, providing nice data abstractions and an elegant way to express functions through pattern matching. Unfortunately, ADTs remain seldom used in low-level programming. One reason is that their increased convenience comes at the cost of abstracting away the exact memory layout of values. Even Rust, which tries to optimize data layout, severely limits control over memory representation. In this article, we present a new approach to specify the data layout of rich data types based on a dual view: a source type, providing a high-level description available in the rest of the code, along with a memory type, providing full control over the memory layout. This dual view allows for better reasoning about memory layout, both for correctness, with dedicated validity criteria linking the two views, and for optimizations that manipulate the memory view. We then provide algorithms to compile constructors and destructors, including pattern matching, to their low-level memory representation. We prove our compilation algorithms correct, implement them in a tool called ribbit that compiles to LLVM IR, and show some early experimental results.

Notes from the program committee:

> This work introduces a type system and a principled, compilation technique for expressing storage format choices and optimizations for algebraic datatypes in a high-level language. This not only improves efficiency of the compiled functional programs, but also provides a degree of control and expressivity that is often only found and implemented ad-hoc in low-level, systems-oriented language. We believe this work and any future works like it are invaluable in expanding capabilities of functional programming by improving the performance capabilities and expressivity.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3607858)

## Algebraic Effects Meet Hoare Logic in Cubical Agda

### Authors: Donnacha Oisín Kidney, Zhixuan Yang, Nicolas Wu

### [Presentation available](https://youtu.be/wXzH9AM5PxQ?si=G4_YLcrCm5R2PUIZ)

This paper presents a novel formalisation of algebraic effects with equations in Cubical Agda. Unlike previous work in the literature that employed setoids to deal with equations, the library presented here uses quotient types to faithfully encode the type of terms quotiented by laws. Apart from tools for equational reasoning, the library also provides an effect-generic Hoare logic for algebraic effects, which enables reasoning about effectful programs in terms of their pre- and post- conditions. A particularly novel aspect is that equational reasoning and Hoare-style reasoning are related by an elimination principle of Hoare logic.

Notes from the program committee:

> This work proves a correspondence between two major approaches to handling effects. It does so in a generic way by operating on a theory of algebraic effects, formalized as syntax quotiented by equations. We believe that this work opens up opportunities to combine lessons, techniques, and advantages from both styles of semantics.

Read the paper [here](https://dl.acm.org/doi/10.1145/3632898)

## Efficient Bottom-Up Synthesis for Programs with Local Variables

### Authors: Xiang Li, Xiangyu Zhou, Rui Dong, Yihong Zhang, Xinyu Wang

### [Presentation available](https://youtu.be/plBSa83AVsM?si=VDzP9qblNF61AzWi)

We propose a new synthesis algorithm that can efficiently search programs with local variables (e.g., those introduced by lambdas). Prior bottom-up synthesis algorithms are not able to evaluate programs with free local variables, and therefore cannot effectively reduce the search space of such programs (e.g., using standard observational equivalence reduction techniques), making synthesis slow. Our algorithm can reduce the space of programs with local variables. The key idea, dubbed lifted interpretation, is to lift up the program interpretation process, from evaluating one program at a time to simultaneously evaluating all programs from a grammar. Lifted interpretation provides a mechanism to systematically enumerate all binding contexts for local variables, thereby enabling us to evaluate and reduce the space of programs with local variables. Our ideas are instantiated in the domain of web automation. The resulting tool, Arborist, can automate a significantly broader range of challenging tasks more efficiently than state-of-the-art techniques including WebRobot and Helena.

Notes from the program committee:

> This work introduces a technique for synthesizing terms with local variables, such as lambdas and loops, in a bottom-up fashion based on finite tree automata by generalizing the program synthesis concept of observational equivalence. We believe that this work will greatly expand the domain of language features that bottom-up synthesis can support.

Read the paper [here](https://dl.acm.org/doi/10.1145/3632894)

# PL Review Program Committee

- Amanda Liu (Conference Chair)
- Dustin Jamner (Program Chair)
- Jaeyeon Won
- Jesse Michel
- Logan Weber (AV Chair)
- Maddy Bowers
- Teodoro Collin
- William Brandon
- Yuka Ikarashi
