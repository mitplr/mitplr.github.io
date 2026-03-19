---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
---

![MIT Programming Languages Review logo](mitplr2026.png){: width="90%" }

# MIT Programming Languages Review Workshop

[Registration](https://forms.gle/kbDrMCRXUeX2STgXA) is now open for the annual MIT PLR Workshop 2026!
Join us in-person or virtually for a fresh lineup of talks and exciting discussion with authors of potentially high-impact, significant works published in recent years at venues!
This year's selected papers are listed below.
For in-person attendance, we will be holding the PL Review on **Friday April 8th**, 2026 at MIT building 34 (50 Vassar St, Cambridge, MA) in the Grier Room (34-401).

The mission of the MIT PL Review is to highlight recent developments that we believe have significant potential to shape the future direction of PL research and/or industry practice. We aim to select papers that may substantially transform the PL community and beyond, with a focus on emerging trends rather than established lines of research. We favor papers whose contributions are broadly accessible (and likely to be appreciated) across the PL community, but we do not limit the papers to those published at PL venues. Our selection process is not meant to provide an objective evaluation of works but rather to highlight and celebrate works that resonated with our committee members.

# Schedule

Time | Event
---|---
9:00-9:30 | Check-In and Opening Remarks |
9:30-9:55 | [Divergence-Aware Testing of Graphics Shader Compiler Back-Ends](https://dl.acm.org/doi/10.1145/3729305)
9:55-10:20 | [An Interactive Debugger for Rust Trait Errors](https://dl.acm.org/doi/10.1145/3729302)
10:20-11:45 | [Still Asking: How Good Are Query Optimizers, Really?](https://dl.acm.org/doi/10.14778/3750601.3760521)
10:45-11:20 | Coffee Break
11:20-11:45 | [CF-GKAT: Efficient Validation of Control-Flow Transformations](https://dl.acm.org/doi/10.1145/3704857)
11:45-12:10 | [Type Theory in Type Theory using a Strictified Syntax](https://dl.acm.org/doi/10.1145/3747535)
12:10-1:20 | Lunch
1:20-1:45 | [Compiling Classical Sequent Calculus to Stock Hardware](https://dl.acm.org/doi/10.1145/3720507)
1:45-2:10 | [Optimizing Datalog for GPU](https://dl.acm.org/doi/10.1145/3669940.3707274)
2:10-2:35 | [Revamping Verilog Semantics for Foundational Verification](https://dl.acm.org/doi/10.1145/3763084)
2:35-3:10 | Coffee Break
3:10-3:35 | [Prompts Are Programs Too! Understanding How Developers Build Software Containing Prompts](https://dl.acm.org/doi/10.1145/3729342)
3:35-4:00 | [Programming by Navigation](https://dl.acm.org/doi/10.1145/3729264)
4:00-5:00 | "All-Stars" Panel

# Selected Papers<sup>\*</sup>
<sup>\*</sup>*To avoid conflicts of interest, no MIT affiliated papers were considered.*


## Divergence-Aware Testing of Graphics Shader Compiler Back-Ends

### Authors: Dongwei Xiao, Shuai Wang, Zhibo Liu, Yiteng Peng, Daoyuan Wu, Zhendong Su

Graphics shaders are the core of modern 3D visual effects, enabling developers to create realistic, real-time rendering of 3D scenes. Shaders are specialized programs written in high-level shading languages like GLSL, and graphics shader compilers translate these high-level shader programs into low-level binaries that run on GPUs. These shader compilers are complex programs with multiple layers: front-end, middle-end, and back-end. Despite significant development efforts from industrial GPU vendors such as NVIDIA and AMD, graphics shader compilers still contain bugs that can impact downstream applications and lead to negative consequences from poor user experience in entertainment to accidents in driving assistance systems. Because they are complex and deep in the compilation pipeline, the back-ends of shader compilers are particularly challenging to test. Our empirical exploration shows that state-of-the-art testing tools for shader compilers do not specifically target the back-ends and are thus ineffective in uncovering back-end bugs. 

This work fills this gap and introduces ShaDiv, an automated testing tool specifically designed to uncover bugs in the back-ends of graphics shader compilers. To this end, ShaDiv generates test inputs with two novel, carefully designed strategies to support the unique computational models of the back-ends, namely control and data flow divergence among GPU threads. ShaDiv deliberately perturbs divergence patterns in both the control and data flow of shader programs to effectively trigger back-end optimizations. Our evaluation of ShaDiv on graphics shader compilers from four mainstream GPU vendors uncovered 12 back-end bugs. Further comparison with existing shader compiler testing tools shows that ShaDiv achieves a 25% coverage increase in the back-end components and finds four times as many back-end bugs.

Notes from the program committee:

> Many works already exist on the topic of automated searches for bugs in compilers targeting massively parallel hardware, but fewer focus on hardware-specific compiler backend bugs (as opposed to algorithmic bugs that could manifest on any reasonable model of a parallel computer). This paper addresses a common backend bug: divergence-aware register allocation bugs. Many GPU compilers will assign a variable to a scalar register, whose state is shared among a group of threads, when they deduce that a variable is non-divergent, i.e. will always hold the same value across said grouping of threads at a given time point. The automated divergence-aware fuzz testing developed by this paper reveals multiple GPU vendors perform this deduction incorrectly, causing unexpected crashes or confusion of one thread's variable values with those of a neighboring thread's. As academic and industry interest in programming languages for specialized hardware accelerators grows, we anticipate that the attack surface for hardware-specific compiler bugs -- and the value of techniques like this paper's -- will be increasing.

Read the paper [here](https://dl.acm.org/doi/10.1145/3729305)


## An Interactive Debugger for Rust Trait Errors

### Authors: Gavin Gray, Will Crichton, Shriram Krishnamurthi

Compiler diagnostics for type inference failures are notoriously bad, and type classes only make the problem worse. By introducing a complex search process during inference, type classes can lead to wholly inscrutable or useless errors. We describe a system, ARGUS, for interactively visualizing type class inferences to help programmers debug inference failures, applied specifically to Rust’s trait system. The core insight of ARGUS is to avoid the traditional model of compiler diagnostics as one-size-fits-all, instead providing the programmer with different views on the search tree corresponding to different debugging goals. ARGUS carefully uses defaults to improve debugging productivity, including interface design (e.g., not showing full paths of types by default) and heuristics (e.g., sorting obligations based on the expected complexity of fixing them). We evaluated ARGUS in a user study where $N = 25$ participants debugged type inference failures in realistic Rust programs, finding that participants using ARGUS correctly localized $2.2\times$ as many faults and localized $3.3\times$ faster compared to not using ARGUS.

Notes from the program committee:

> This paper addresses a significant UI/UX problem that plagues complex type systems: how do you communicate to a user a type resolution failure, when correctly resolving types is a search process? The solution (for Rust Traits in particular) is Argus, a system where an interactive view is provided into the search process, pruning away irrelevant information, and letting the user see why the path they envision is not being compiled properly. Empirical results demonstrate that this outperforms the standard diagnostic at trait error localization and resolution.

Read the paper [here](https://dl.acm.org/doi/10.1145/3729302)


## Still Asking: How Good Are Query Optimizers, Really?

### Authors: Viktor Leis, Andrey Gubichev, Atanas Mirchev, Peter Boncz, Alfons Kemper, Thomas Neumann

This retrospective revisits our 2015 PVLDB paper How Good Are Query Optimizers, Really?, which challenged the prevailing notion that query optimization was a solved problem. By designing the Join Order Benchmark (JOB) and conducting a series of systematic experiments, we empirically disentangled the contributions of plan enumeration, cost modeling, and cardinality estimation. Our findings showed that cardinality estimation errors are widespread and often the dominant factor behind poor query plans, while cost models and enumeration strategies matter comparatively less. The benchmark and methodology helped refocus the community’s attention on cardinality estimation and led to a resurgence of research in this area, including learned and AI-based approaches. We reflect on the role of experiments and benchmarking in database research, survey developments in query optimization over the past decade, and discuss open challenges around robustness, adaptive execution, and realistic workloads.

Notes from the program committee:

> This paper revisits a classic: How good are query optimizers? We call attention to the revisit because in the last decade the question has found new relevance in programming languages. As a direct subject (e.g., a resurgence of work on compilers for sparse tensor algebra and other irregular workloads) or as consumers (e.g., utilizing e-graphs or other database representations of classes of programs), programming languages researchers also ought to be worrying: how good are query optimizers, really? This work highlights that at the core of the problem is (still) cardinality estimation, which is often not addressed in PL works that rely on or aim to impact database performance. Thus, we call attention to this work, which provides a clear and recent outline of some of the problems, solutions, methodologies found within the fundamental problem of query optimization.

Read the paper [here](https://dl.acm.org/doi/10.14778/3750601.3760521)


## CF-GKAT: Efficient Validation of Control-Flow Transformations

### Authors: Cheng Zhang, Tobias Kappé, David E. Narváez, Nico Naus

Guarded Kleene Algebra with Tests (GKAT) provides a sound and complete framework to reason about trace equivalence between simple imperative programs. However, there are still several notable limitations. First, GKAT is completely agnostic with respect to the meaning of primitives, to keep equivalence decidable. Second, GKAT excludes non-local control flow such as $\texttt{goto}$, $\texttt{break}$, and $\texttt{return}$. To overcome these limitations, we introduce *Control-Flow GKAT* (*CF-GKAT*), a system that allows reasoning about programs that include non-local control flow as well as hardcoded values. CF-GKAT is able to soundly and completely verify trace equivalence of a larger class of programs, while preserving the nearly-linear efficiency of GKAT. This makes CF-GKAT suitable for the verification of control-flow manipulating procedures, such as decompilation and $\texttt{goto}$-elimination. To demonstrate CF-GKAT’s abilities, we validated the output of several highly non-trivial program transformations, such as Erosa and Hendren’s $\texttt{goto}$-elimination procedure and the output of Ghidra decompiler. CF-GKAT opens up the application of Kleene Algebra to a wider set of challenges, and provides an important verification tool that can be applied to the field of decompilation and control-flow transformation.

Notes from the program committee:

> This work introduces a system that enables efficient algebraic reasoning about programs involving nonlocal control flow and hardcoded variables. It is the first work to give a direct algebraic representation of nonlocal control flow, via a reduction to GKAT, yielding a nearly-linear decision procedure for verifying trace equivalence of programs with nonlocal control flow and indicator variables. It demonstrates applications by validating the output of several nontrivial program transformations, such as decompilation and goto elimination. 

Read the paper [here](https://dl.acm.org/doi/10.1145/3704857)


## Type Theory in Type Theory using a Strictified Syntax

### Authors: Ambrus Kaposi, Loïc Pujet

The metatheory of dependent types has seen a lot of progress in recent years. In particular, the development of categorical gluing finally lets us work with *semantic* presentations of type theory (such as categories with families) to establish fundamental properties of type theory such as canonicity and normalisation. However, proofs by gluing have yet to reach the stage of computer formalisation: formal proofs for the metatheory of dependent types are still stuck in the age of tedious syntactic proofs. The main reason for this is that semantic presentations of type theory are defined using sophisticated indexed inductive types, which are prone to “transport hell”. In this paper, we introduce a new technique to work with CwFs in intensional type theory without getting stuck in transport hell. More specifically, we construct an alternative presentation of the initial CwF which encodes the substitutions as metatheoretical functions. This has the effect of strictifying all the equations that are involved in the substitution calculus, which greatly reduces the need for transports. As an application, we use our strictified initial CwF to give a short and elegant proof of canonicity for a type theory with dependent products and booleans with large elimination. The resulting proof is fully formalised in Agda.

Notes from the program committee:

> In mechanized metatheory for dependent types, substitution poses a critical concern. Despite being an extensively studied concept, substitution manipulation comprises a significant proportion of the labor in proving critical properties via existing methods. This work demonstrates how to eliminate manual substitution manipulation by developing a model where the equations of substitution are definitional. This allows the theorem prover to automatically handle substitution, avoiding the need for manual manipulation. Going forward, we expect this approach to become a key tool in modern formalizations of type theory.

Read the paper [here](https://dl.acm.org/doi/10.1145/3747535)


## Compiling Classical Sequent Calculus to Stock Hardware: The Duality of Compilation

### Authors: Philipp Schuster, Marius Müller, Klaus Ostermann, Jonathan Immanuel Brachthäuser

Compiler intermediate representations have to strike a balance between being high-level enough to allow for easy translation of surface languages into them and being low-level enough to make code generation easy. An intermediate representation based on a logical system typically has the former property and additionally satisfies several meta-theoretical properties which are valuable when optimizing code. Recently, classical sequent calculus, which is widely recognized and impactful within the fields of logic and proof theory, has been proposed as a natural candidate in this regard, due to its symmetric treatment of data and control flow. For such a language to be useful, however, it must eventually be compiled to machine code. In this paper, we introduce an intermediate representation that is based on classical sequent calculus and demonstrate that this language can be directly translated to conventional hardware. We provide both a formal description and an implementation. Preliminary performance evaluations indicate that our approach is viable.

Notes from the program committee:

> Sequent calculi not only naturally capture both the constructs of traditional functional languages and effectful behavior, but are also amenable to formal reasoning and rewriting in a way that should make them a good candidate for compiler intermediate representations (IRs). However, despite their longstanding presence in the literature, they have had limited success in this field because compilers had no effective way to lower an optimized sequent calculus program to assembly. This paper fills this gap by defining a concise IR for sequent calculus that lowers naturally to assembly. With this innovation, it seems quite possible that sequent calculi become a viable choice for compiling functional languages, especially those with control effects.

Read the paper [here](https://dl.acm.org/doi/10.1145/3720507)


## Optimizing Datalog for the GPU

### Authors: Yihao Sun, Ahmedur Rahman Shovon, Thomas Gilray, Sidharth Kumar, Kristopher Micinski

Modern Datalog engines (e.g., LogicBlox, Soufflé, ddlog) enable their users to write declarative queries which compute recursive deductions over extensional facts, leaving high-performance operationalization (query planning, semi-naïve evaluation, and parallelization) to the engine. Such engines form the backbone of modern high-throughput applications in static analysis, network monitoring, and social-media mining. In this paper, we present a methodology for implementing a modern in-memory Datalog engine on data center GPUs, allowing us to achieve significant (up to 45×) gains compared to Soufflé (a modern CPU-based engine) on context-sensitive points-to analysis of PostgreSQL. We present GPUlog, a Datalog engine backend that implements iterated relational algebra kernels over a novel range-indexed data structure we call the hash-indexed sorted array (HISA). HISA combines the algorithmic benefits of incremental range-indexed relations with the raw computation throughput of operations over dense data structures. Our experiments show that GPUlog is significantly faster than CPU-based Datalog engines while achieving a favorable memory footprint compared to contemporary GPU-based joins.

Notes from the program committee:

> This paper explores how modern Datalog engines can be redesigned for accelerator hardware. It introduces a GPU-backed Datalog engine built around a novel data structure called hash-indexed sorted array (HISA). HISA enables efficient execution of sparse relational workloads by combining the benefits of constant-time indexed access with dense, range-structured data layouts. By rethinking how a foundational declarative programming technology maps to GPUs, the work highlights a growing intersection between programming languages, program analysis infrastructure, and accelerator-aware system design, illustrating how PL implementation techniques can evolve alongside modern hardware trends.

Read the paper [here](https://dl.acm.org/doi/10.1145/3669940.3707274)


## Revamping Verilog Semantics for Foundational Verification

### Authors: Joonwon Choi, Jaewoo Kim, Jeehoon Kang

In formal hardware verification, particularly for Register-Transfer Level (RTL) designs in Verilog, model checking has been the predominant technique. However, it suffers from state explosion, limited expressive power, and a large trusted computing base (TCB). Deductive verification offers greater expressive power and enables foundational verification with a minimal TCB. Nevertheless, Verilog’s standard semantics, characterized by its nondeterministic and global scheduling, pose significant challenges to its application. 

To address these challenges, we propose a new Verilog semantics designed to facilitate deductive verification. Our semantics is based on least fixpoints to enable cycle-level functional evaluation and modular reasoning. For foundational verification, we prove our semantics equivalent to the standard scheduling semantics for synthesizable designs. We demonstrate the benefits of our semantics with a modular verification of a pipelined RISC-V processor’s functional correctness and progress guarantees. All our results are mechanized in Rocq.

Notes from the program committee:

> This paper tackles a common challenge in traditional hardware verification: Verilog's standard semantics are incompatible with modular deductive verification. While model checking dominates hardware verification, it suffers from state explosion and limited expressiveness. Deductive verification promises foundational correctness guarantees with minimal trusted computing base, but Verilog's nondeterministic scheduling has made this impractical. This work introduces cycle-level functional semantics based on least fixpoints and proves them equivalent to the IEEE standard for synthesizable designs. The modular semantics enable compositional reasoning, demonstrated through a fully verified pipelined RISC-V processor in Rocq. We highlight this work as the first formal Verilog semantics that is simultaneously proven sound, deterministic, and modular—bridging the gap between industry-standard RTL languages and foundational verification techniques.

Read the paper [here](https://dl.acm.org/doi/10.1145/3763084)


## Prompts Are Programs Too! Understanding How Developers Build Software Containing Prompts

### Authors: Jenny T. Liang, Melissa Lin, Nikitha Rao, Brad A. Myers

Generative pre-trained models power intelligent software features used by millions of users controlled by developer-written natural language prompts. Despite the impact of prompt-powered software, little is known about its development process and its relationship to programming. In this work, we argue that some prompts are programs and that the development of prompts is a distinct phenomenon in programming known as "*prompt programming*". We develop an understanding of prompt programming using Straussian grounded theory through interviews with 20 developers engaged in prompt development across a variety of contexts, models, domains, and prompt structures. We contribute 15 observations to form a preliminary understanding of current prompt programming practices. For example, rather than building mental models of code, prompt programmers develop mental models of the foundation model (FM)’s behavior on the prompt by interacting with the FM. While prior research shows that experts have well-formed mental models, we find that prompt programmers who have developed dozens of prompts still struggle to develop reliable mental models. Our observations show that prompt programming differs from traditional software development, motivating the creation of prompt programming tools and providing implications for software engineering stakeholders.

Notes from the program committee:

> This paper rigorously investigates and establishes prompting as a programming paradigm through structured observational study of program developers’ prompting workflow. While prompting has been vibe-accepted as a new way to write programs and software, we identify this work as a prominent and thorough formal study on what it means for prompting to be an act of programming. The study also exposes the gap in existing programming systems and programming tools, setting an empirically-based direction for future research in reasoning about natural language programs.

Read the paper [here](https://dl.acm.org/doi/10.1145/3729342)


## Programming by Navigation

### Authors: Justin Lubin, Parker Ziegler, Sarah E. Chasins

When a program synthesis task starts from an ambiguous specification, the synthesis process often involves an iterative specification refinement process. We introduce the Programming by Navigation Synthesis Problem, a new synthesis problem adapted specifically for supporting iterative specification refinement in order to find a *particular* target solution. In contrast to prior work, we prove that synthesizers that solve the Programming by Navigation Synthesis Problem show *all* valid next steps (**Strong Completeness**) and *only* valid next steps (**Strong Soundness**). To meet the demands of the Programming by Navigation Synthesis Problem, we introduce an algorithm to turn a type inhabitation oracle (in the style of classical logic) into a fully constructive program synthesizer. We then define such an oracle via sound compilation to Datalog. Our empirical evaluation shows that this technique results in an efficient Programming by Navigation synthesizer that solves tasks that are either impossible or too large for baselines to solve. Our synthesizer is the first to guarantee that its specification refinement process satisfies both **Strong Completeness** and **Strong Soundness**.

Notes from the program committee:

> Having non-programmer users guide program synthesis is a longstanding problem, with inherent tradeoffs between giving too many choices (which might be nonsensical or undesirable) and too few (cutting off the expressive capacity). In this paper, the system Honeybee is developed, which, given a language with primitives that use restricted dependent types, is able to determine which choices in expanding a program will lead to any workable programs in the future, and present only these choices to the user. When paired with the correct language, this can lead to the automatic generation of powerful interfaces for writing domain-specific programs without needing to write any code.

Read the paper [here](https://dl.acm.org/doi/10.1145/3729264)


You can see last year's program [here](plr2025.md).

# PL Review Program Committee

- David Akeley
- Ellie Cheng
- Teodoro Collin
- Vivian Ding
- Kavi Gupta (Program Chair)
- Dustin Jamner
- Amanda Liu 
- Jiazheng Liu (Conference Chair)
- Upamanyu Sharma
