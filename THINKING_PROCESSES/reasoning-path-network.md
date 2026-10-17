# Reasoning-Path Network

## Hypothesis

A general execution runtime can combine many independently executable formulae into paths. A formula's output can update shared state, create a relationship, update a hypothesis probability, or activate dependent units. The same runtime can handle small and large tasks while varying active computation with task difficulty.

## Abstract model

Represent the network as a directed graph `G = (V, E)`:

- `V`: typed executable formula units;
- `E`: permitted data/dependency links;
- `s_t`: shared state at execution step `t`;
- `A_t`: formulae activated at step `t`.

A unit evaluates `y_i = f_i(x_i, s_t)`. Its typed output may update state and make downstream units eligible to run. The runtime should use event-driven or dependency-driven scheduling rather than activating the whole library indiscriminately.

## Runtime responsibilities

- Validate input/output schemas and units.
- Enforce preconditions and permissions.
- Schedule units when required inputs are available.
- Record intermediate values and causal/execution traces.
- Prune paths using constraints, relevance, cost, and evidence.
- Track probabilities without confusing them with verified facts.
- Detect cycles; enforce budgets, timeouts, and stopping conditions.
- Return a typed result or identify unresolved inputs.

## Learning opportunities

The system may learn which paths are useful, what context to retrieve, when to branch, when to stop, and which formula compositions generalize. It may also propose new formulae, but proposed units need type checks, sandboxed execution, tests, and provenance before they become trusted components.

## Efficiency hypothesis

Storage size is distinct from active cost. For a task, approximate work as the sum of active-unit cost, connection/scheduling overhead, search cost, and learning/verification cost. Selective activation, bounded search, caching, and reuse may reduce cost. Dense interactions, repeated loops, or combinatorial path exploration may increase it.

## Baseline experiment

Create a small synthetic environment with 5–10 formula units: arithmetic, condition checking, probability update, relation creation, and route selection. Compare a fixed hand-written path, exhaustive search, and selective routing on held-out tasks.

Measure success rate, generalization, active units, paths explored, latency, and error recovery. Do not infer intelligence from the number of connected units.

## Related ideas

Related engineering families include dataflow graphs, rule engines, blackboard architectures, program synthesis, planning, and tool-using agents. These are comparison points, not proof that this particular design works.
