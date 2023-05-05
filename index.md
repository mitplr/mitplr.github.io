---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
---

![MIT Programming Languages Review logo](mitplr2023.png){: width="90%" }

# MIT Programming Languages Review

The mission of the MIT PL Review is to highlight recent developments that we believe have significant potential to shape the future direction of PL research and/or industry practice. We aim to select papers that may substantially transform the PL community and beyond, with a focus on emerging trends rather than established lines of research. We favor papers whose contributions are broadly accessible (and likely to be appreciated) across the PL community, but we do not limit the papers to those published at PL venues. Our selection process is not meant to provide an objective evaluation of works but rather to highlight and celebrate works that resonated with our committee members.

We will be holding the PL Review on May 30, 2023 at MIT in the Ray and Maria Stata Center (32 Vassar Street), room 32-155.
The event will begin at 9:00am with talks starting at 10:00am and concluding at 5:00pm.
Virtual attendees can participate though our Slack workspace and attend talks via Zoom.
Please [register](https://mit.co1.qualtrics.com/jfe/form/SV_7Qy1V7rAlX1IASi) by May 15 to participate.

# Schedule

Time | Event
---|---
9:00-9:45 | Breakfast |
9:45-10:00 | Opening Remarks
10:00-10:30 | Satisfiability modulo fuzzing: a synergistic combination of SMT solving and fuzzing
10:30-11:00 | Staged Compilation with Two-Level Type Theory
11:00-11:30 | A Compositional Atlas of Tractable Circuit Operations for Probabilistic Inference 
11:30-12:30 | Lunch
12:30-1:00 | The Role of Working Memory in Program Tracing
1:00-1:30 | Predictable Accelerator Design with Time-Sensitive Affine Types
1:30-2:00 | Frequent Background Polling on a Shared Thread, using Light-Weight Compiler Interrupts
2:00-2:30 | Coffee Break
2:30-3:00 | PDL: A High-Level Hardware Design Language for Pipelined Processors
3:00-3:30 | A Flexible Type System for Fearless Concurrency
3:30-4:00 | You Only Linearize Once
4:00-5:00 | MIT Faculty Panel: *Future of Programming Languages*

# Selected Papers<sup>*</sup>
<sup>*</sup> *To avoid conflicts of interest, no MIT affiliated papers were considered.*

## Satisfiability modulo fuzzing: a synergistic combination of SMT solving and fuzzing

### Authors: Sujit Kumar Muduli, Subhajit Roy

Programming languages and software engineering tools routinely encounter components that are difficult to reason on via formal techniques or whose formal semantics are not even available—third-party libraries, inline assembly code, SIMD instructions, system calls, calls to machine learning models, etc. However, often access to these components is available as input-output oracles—interfaces are available to query these components on certain inputs to receive the respective outputs. We refer to such functions as closed-box functions. Regular SMT solvers are unable to handle such closed-box functions.

We propose Sādhak, a solver for SMT theories modulo closed-box functions. Our core idea is to use a synergistic combination of a fuzzer to reason on closed-box functions and an SMT engine to solve the constraints pertaining to the SMT theories. The fuzz and the SMT engines attempt to converge to a model by exchanging a rich set of interface constraints that are relevant and interpretable by them. Our implementation, Sādhak, demonstrates a significant advantage over the only other solver that is capable of handling such closed-box constraints: Sādhak solves 36.45% more benchmarks than the best-performing mode of this state-of-the-art solver and has 5.72x better PAR-2 score; on the benchmarks that are solved by both tools, Sādhak is (on an average) 14.62x faster.

Notes from the program committee:

> This paper presents a neat idea to unify two widely used, highly impactful "black-box" techniques. Many papers in PL rely on SMT solvers, but very few actually advance the state of the art. We believe the ideas in this work will open the applicability of SMT solvers to a wider range of applications, and also inspire deeper inquiries into the tools we often take for granted.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3563332)

## Staged Compilation with Two-Level Type Theory

### Authors: András Kovács
  
The aim of staged compilation is to enable metaprogramming in a way such that we have guarantees about the well-formedness of code output, and we can also mix together object-level and meta-level code in a concise and convenient manner. In this work, we observe that two-level type theory (2LTT), a system originally devised for the purpose of developing synthetic homotopy theory, also serves as a system for staged compilation with dependent types. 2LTT has numerous good properties for this use case: it has a concise specification, well-behaved model theory, and it supports a wide range of language features both at the object and the meta level. First, we give an overview of 2LTT's features and applications in staging. Then, we present a staging algorithm and prove its correctness. Our algorithm is "staging-by-evaluation", analogously to the technique of normalization-by-evaluation, in that staging is given by the evaluation of 2LTT syntax in a semantic domain. The staging algorithm together with its correctness constitutes a proof of strong conservativity of 2LLT over the object theory. To our knowledge, this is the first description of staged compilation which supports full dependent types and unrestricted staging for types.
  
Notes from the program committee:

> We believe that this work will broaden the scope of metaprogramming for dependent type theory, a key feature closely tied to the practical use of said theories. The current state of the art, embodied by tactic systems in theorem provers like Coq and Lean, is limited since tactics live in an untrusted world outside the space of verifiable programs. We expect that by integrating metaprogramming into the core of a theorem prover, such systems can simultaneously increase the scope of metaprogramming features while moving some key existing features from the trusted kernel into verified libraries.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3547641)
  

## A Compositional Atlas of Tractable Circuit Operations for Probabilistic Inference

### Authors: Antonio Vergari, YooJung Choi, Anji Liu, Stefano Teso, Guy Van den Broeck

Circuit representations are becoming the lingua franca to express and reason about tractable generative and discriminative models. In this paper, we show how complex inference scenarios for these models that commonly arise in machine learning---from computing the expectations of decision tree ensembles to information-theoretic divergences of sum-product networks---can be represented in terms of tractable modular operations over circuits. Specifically, we characterize the tractability of simple transformations---sums, products, quotients, powers, logarithms, and exponentials---in terms of sufficient structural constraints of the circuits they operate on, and present novel hardness results for the cases in which these properties are not satisfied. Building on these operations, we derive a unified framework for reasoning about tractable models that generalizes several results in the literature and opens up novel tractable inference scenarios.
  
Notes from the program committee:

> This paper stands out for its axiomatic approach, and we appreciate that its theoretical contributions will be palatable to a wide audience. It also provides a solid foundation for future developments in probabilistic circuits, a class of efficient probabilistic programs. We hope that this work can motivate the programming languages community to explore ways in which the techniques from our field apply to the domain of inference.


Read the paper [here](https://proceedings.neurips.cc/paper_files/paper/2021/hash/6e01383fd96a17ae51cc3e15447e7533-Abstract.html)

## The Role of Working Memory in Program Tracing

### Authors: Will Crichton, Maneesh Agrawala, Pat Hanrahan

Program tracing, or mentally simulating a program on concrete inputs, is an important part of general program comprehension. Programs involve many kinds of virtual state that must be held in memory, such as variable/value pairs and a call stack. In this work, we examine the influence of short-term working memory (WM) on a person’s ability to remember program state during tracing. We first confirm that previous findings in cognitive psychology transfer to the programming domain: people can keep about 7 variable/value pairs in WM, and people will accidentally swap associations between variables due to WM load. We use a restricted focus viewing interface to further analyze the strategies people use to trace through programs, and the relationship of tracing strategy to WM. Given a straight-line program, we find half of our participants traced a program from the top-down line-by-line (linearly), and the other half start at the bottom and trace upward based on data dependencies (on-demand). Participants with an on-demand strategy made more WM errors while tracing straight-line code than with a linear strategy, but the two strategies contained an equal number of WM errors when tracing code with functions. We conclude with the implications of these findings for the design of programming tools: first, programs should be analyzed to identify and refactor human-memory-intensive sections of code. Second, programming environments should interactively visualize variable metadata to reduce WM load in accordance with a person’s tracing strategy. Third, tools for program comprehension should enable externalizing program state while tracing.

Notes from the program committee:

> This work leverages well-established concepts from cognitive psychology regarding working memory to explore the types of techniques and mistakes that affect programmers as they conduct program tracing. With this methodology, the authors were able to formulate and test well-supported claims about tracing errors based on existing psychology principles and make principled recommendations for the future design of programming tools. Not only are the conclusions drawn by this project potentially influential on future tool design, we believe this kind of interdisciplinarily-motivated approach will be more widely adopted.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3411764.3445257)

## Predictable Accelerator Design with Time-Sensitive Affine Types

### Authors: Rachit Nigam, Sachille Atapattu, Samuel Thomas, Zhijing Li, Theodore Bauer, Yuwei Ye, Apurva Koti, Adrian Sampson, Zhiru Zhang

Field-programmable gate arrays (FPGAs) provide an opportunity to co-design applications with hardware accelerators, yet they remain difficult to program. High-level synthesis (HLS) tools promise to raise the level of abstraction by compiling C or C++ to accelerator designs. Repurposing legacy software languages, however, requires complex heuristics to map imperative code onto hardware structures. We find that the black-box heuristics in HLS can be unpredictable: changing parameters in the program that should improve performance can counterintuitively yield slower and larger designs. This paper proposes a type system that restricts HLS to programs that can predictably compile to hardware accelerators. The key idea is to model consumable hardware resources with a time-sensitive affine type system that prevents simultaneous uses of the same hardware structure. We implement the type system in Dahlia, a language that compiles to HLS C++, and show that it can reduce the size of HLS parameter spaces while accepting Pareto-optimal designs.

Notes from the program committee:

> In the world of high-performance systems, types and formal methods have gained traction as tools to prove correctness and soundness of optimizations. This project proposes a type system that provides a principled way to predictably reason about accelerator design performance and shore down the vast design space. This type of work demonstrates the potential of programming languages methods in HPC spaces to not only reason about correctness but also performance.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3385412.3385974)

## PDL: A High-Level Hardware Design Language for Pipelined Processors

### Authors: Drew Zagieboylo, Charles Sherk, Gookwon Edward Suh, Andrew C. Myers  

Processors are typically designed in Register Transfer Level (RTL) languages, which give designers low-level control over circuit structure and timing. To achieve good performance, processors are pipelined, with multiple instructions executing concurrently in different parts of the circuit. Thus even though processors implement a fundamentally sequential specification (the instruction set architecture), the implementation is highly concurrent. The interactions of multiple instructions—potentially speculative—can cause incorrect behavior.

We present PDL, a novel hardware description language targeted at the construction of pipelined processors. PDL provides one-instruction-at-a-time semantics; the first language to enforce that the generated pipelined circuit has the same behavior as a sequential specification. This enforcement facilitates design-space exploration. Adding or removing pipeline stages, moving operations across stages, or otherwise chang ing pipeline structure normally requires careful analysis of bypass paths and stall logic; with PDL, this analysis is handled by the PDL compiler. At the same time, PDL still offers designers fine-grained control over performance-critical microarchitectural choices such as timing of operations, data forwarding, and speculation. We demonstrate PDL’s expressive power and ease of design exploration by implementing several RISC-V cores with differing microarchitectures. Our results show that PDL does not impose significant performance or area overhead compared to a standard HDL.


Notes from the program committee:

> This paper brings safety via abstraction, a key benefit of programming language techniques, to hardware pipeline design. Existing tooling for hardware design does not adequately support safety guarantees, and we hope that this work will push the field towards the benefits of static enforcement mechanisms in this critical application domain without sacrificing performance goals.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3519939.3523455)

## A Flexible Type System for Fearless Concurrency

### Authors: Mae Milano, Joshua Turcotti, Andrew C. Myers

This paper proposes a new type system for concurrent programs, allowing threads to exchange complex object graphs without risking destructive data races. While this goal is shared by a rich history of past work, existing solutions either rely on strictly enforced heap invariants that prohibit natural programming patterns or demand pervasive annotations even for simple programming tasks. As a result, past systems cannot express intuitively simple code without unnatural rewrites or substantial annotation burdens. Our work avoids these pitfalls through a novel type system that provides sound reasoning about separation in the heap while remaining flexible enough to support a wide range of desirable heap manipulations. This new sweet spot is attained by enforcing a heap domination invariant similarly to prior work, but tempering it by allowing complex exceptions that add little annotation burden. Our results include: (1) code examples showing that common data structure manipulations which are difficult or impossible to express in prior work are natural and direct in our system, (2) a formal proof of correctness demonstrating that well-typed programs cannot encounter destructive data races at run time, and (3) an efficient type checker implemented in Gallina and OCaml.

Notes from the program committee:

> This work adds support for a large and important class of data structures to the ecosystem of practical substructural languages. Given the great success of Rust in the last decade and the clear desire for better ways to represent these structures in the Rust ecosystem, we believe that the type system designed in this paper will influence the next generation of substructural languages and eventually make its way into standard industry use.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3519939.3523443)

## Frequent Background Polling on a Shared Thread, using Light-Weight Compiler Interrupts

### Authors: Nilanjana Basu, Claudio Montanari, Jakob Eriksson

Recent work in networking, storage and multi-threading has demonstrated improved performance and scalability by replacing kernel-mode interrupts with high-rate user-space polling. Typically, such polling is performed by a dedicated core. Compiler Interrupts (CIs) instead enable efficient, automatic high-rate polling on a shared thread, which performs other work between polls. CIs are instrumentation-based and light-weight, allowing frequent interrupts with little performance impact. For example, when targeting a 5,000 cycle interval, the median overhead of our fastest CI design is 4% vs. 800% for hardware interrupts, across programs in the SPLASH-2, Phoenix and Parsec benchmark suites running with 32 threads. We evaluate CIs on three systems-level applications: (a) kernel bypass networking with mTCP, (b) joint kernel bypass networking and CPU scheduling with Shenango, and (c) delegation, a message-passing alternative to locking, with FFWD. For each application, we find that CIs offer compelling qualitative and quantitative improvements over the current state of the art. For example, CI-based mTCP achieves ≈2× stock mTCP throughput on a sample HTTP application.

Notes from the program committee:

> This paper brings the attention of the PL community towards advances in hardware and recent trends in systems research. We believe this paper provides an example of how compiler techniques can be used to remove the cost of abstractions that were previously handled at runtime by hardware. We also hope this work will motivate further exploration of more such use cases for compiler techniques. 

Read the paper [here](https://dl.acm.org/doi/10.1145/3453483.3454107)

## You Only Linearize Once

### Authors: Alexey Radul, Adam Paszke, Roy Frostig, Matthew J. Johnson, Dougal Maclaurin

Automatic differentiation (AD) is conventionally understood as a family of distinct algorithms, rooted in two “modes”—forward and reverse—which are typically presented (and implemented) separately. Can there be only one? Following up on the AD systems developed in the JAX and Dex projects, we formalize a decomposition of reverse-mode AD into (i) forward-mode AD followed by (ii) unzipping the linear and non-linear parts and then (iii) transposition of the linear part.

To that end, we define a (substructurally) linear type system that can prove a class of functions are (algebraically) linear. Our main results are that forward-mode AD produces such linear functions, and that we can unzip and transpose any such linear function, conserving cost, size, and linearity. Composing these three transformations recovers reverse-mode AD. This decomposition also sheds light on checkpointing, which emerges naturally from a free choice in unzipping let expressions. As a corollary, checkpointing techniques are applicable to general-purpose partial evaluation, not just AD.

We hope that our formalization will lead to a deeper understanding of automatic differentiation and that it will simplify implementations, by separating the concerns of differentiation proper from the concerns of gaining efficiency (namely, separating the derivative computation from the act of running it backward).

Notes from the program committee:

> The principled application of type theory in this paper yields one of the cleanest frameworks for deep learning. We believe there is much untapped research potential within ML for PL researchers, and are excited to see more work of a similar flavor in the coming years.

Read the paper [here](https://dl.acm.org/doi/abs/10.1145/3571236)


# PL Review Program Committee

- Ajay Brahmakshatriya
- Alex Renda
- Amanda Liu (Conference Chair)
- Charles Jin
- Dustin Jamner (Program Chair)
- Matt Bowers
- Tom Chen
- Yuka Ikarashi
