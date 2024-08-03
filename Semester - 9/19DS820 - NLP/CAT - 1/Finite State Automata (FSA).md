Finite State Automata, also known as Finite State Machines, are abstract models used to recognize patterns and represent regular languages. They consist of five key elements:

1. Q: A finite set of states
2. Σ: A finite set of input symbols
3. q0: An initial state (q0 ∈ Q)
4. F: A set of final or accepting states (F ⊆ Q)
5. δ: A transition function

FSAs are primarily categorized into two types: Deterministic Finite Automata (DFA) and Non-deterministic Finite Automata (NFA).

## Deterministic Finite Automata (DFA)

A DFA is a type of FSA where:

1. For each input symbol and current state, there is exactly one next state.
2. Null (ε) moves are not allowed.

**Formal Definition:**
A DFA is represented as a 5-tuple (Q, Σ, δ, q0, F), where:
- Q: Set of all states
- Σ: Set of input symbols
- δ: Transition function, defined as δ: Q × Σ → Q
- q0: Initial state
- F: Set of final states

**Example:**
Consider a DFA that accepts strings ending with "ab":

1. States: Q = {q0, q1, q2}
2. Input symbols: Σ = {a, b}
3. Initial state: q0
4. Final state: F = {q2}
5. Transition function:
   - δ(q0, a) = q1
   - δ(q0, b) = q0
   - δ(q1, a) = q1
   - δ(q1, b) = q2
   - δ(q2, a) = q1
   - δ(q2, b) = q0

This DFA would accept strings like "ab", "aab", "bab", but reject strings like "a", "b", "ba"[1].

## Non-deterministic Finite Automata (NFA)

An NFA is a type of FSA where:

1. For each input symbol and current state, there can be zero, one, or multiple next states.
2. Null (ε) moves are allowed.

**Formal Definition:**
An NFA is represented as a 5-tuple (Q, Σ, δ, q0, F), where:
- Q: Set of all states
- Σ: Set of input symbols
- δ: Transition function, defined as δ: Q × (Σ ∪ {ε}) → 2^Q
- q0: Initial state
- F: Set of final states

**Example:**
Consider an NFA that accepts strings containing "01":

1. States: Q = {q0, q1, q2}
2. Input symbols: Σ = {0, 1}
3. Initial state: q0
4. Final state: F = {q2}
5. Transition function:
   - δ(q0, 0) = {q0, q1}
   - δ(q0, 1) = {q0}
   - δ(q1, 1) = {q2}
   - δ(q2, 0) = {q2}
   - δ(q2, 1) = {q2}

This NFA would accept strings like "01", "001", "0101", but reject strings like "0", "1", "10"[4].

**Key Differences between DFA and NFA:**

1. Determinism: DFAs have a single next state for each input, while NFAs can have multiple or no next states.
2. ε-moves: NFAs allow ε-moves, DFAs don't.
3. Ease of design: NFAs are often easier to design for complex patterns.
4. State complexity: Converting an NFA to a DFA may result in an exponential increase in the number of states[2].

## Context-Free Grammar (CFG)

A Context-Free Grammar is a formal grammar used to describe the syntax of languages. It's more expressive than regular languages and is commonly used in compiler design and natural language processing.

**Formal Definition:**
A CFG is represented as a 4-tuple (V, T, P, S), where:
- V: Set of non-terminal symbols
- T: Set of terminal symbols
- P: Set of production rules
- S: Start symbol (S ∈ V)

**Key Characteristics:**
1. Every production rule is of the form A → α, where A is a single non-terminal symbol and α is a string of terminals and/or non-terminals.
2. The left-hand side of each production rule must be a single non-terminal symbol.

**Example:**
Consider a CFG for simple arithmetic expressions:

1. V = {E, T, F}
2. T = {+, *, (, ), id}
3. S = E
4. Production rules P:
   - E → E + T | T
   - T → T * F | F
   - F → (E) | id

This grammar can generate expressions like "id + id * id" or "(id + id) * id"[5].

**Limitations of CFG:**
1. Less expressive than natural languages
2. Can be ambiguous
3. May have exponential time complexity for parsing
4. Less precise error reporting compared to more advanced grammars

Sources
[1] Deterministic Finite Automata - DFA - Javatpoint https://www.javatpoint.com/deterministic-finite-automata
[2] Introduction of Finite Automata - GeeksforGeeks https://www.geeksforgeeks.org/introduction-of-finite-automata/
[3] Finite State machine - javatpoint https://www.javatpoint.com/finite-state-machine
[4] Non-Deterministic Finite Automata - NFA - Javatpoint https://www.javatpoint.com/non-deterministic-finite-automata
[5] What is Context-Free Grammar? - GeeksforGeeks https://www.geeksforgeeks.org/what-is-context-free-grammar/
