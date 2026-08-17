---
name: cld-authoring
description: Create, inspect, edit, lay out, annotate, and save causal loop diagrams in CLDMaker through its MCP tools. Use when a user asks to build or revise a CLD, work with a .cld file, identify reinforcing or balancing loops, or explain feedback structure in an existing diagram. For research-derived models, also use cld-research-to-diagram.
---

# CLD Authoring

Use CLDMaker's semantic MCP operations. Let the app own identifiers, loop classification, and geometry.

## Authoring workflow

1. Identify the target diagram.
   - Call `list_windows` when the user refers to an open diagram.
   - Call `attach_diagram` with the exact saved path to edit a user-created window.
   - Call `open_diagram` for an existing `.cld` file that is not open.
   - Call `create_diagram` for a new model.
   - Call `focus_diagram` for the diagram actively co-authored with the user.

2. Define the causal structure.
   - Name nodes as quantities that can increase or decrease.
   - Keep one concept per node.
   - Add a directed link only when a causal mechanism supports it.
   - Use `+` when cause and effect move in the same direction, all else equal.
   - Use `-` when cause and effect move in opposite directions, all else equal.
   - Surface ambiguous direction or polarity instead of guessing.

3. Create the structure atomically.
   - Prefer `batch_create` for more than one new node.
   - Give each new node a temporary id and use those ids in the same batch's links.
   - Use `add_node` and `add_link` for deliberate incremental edits.
   - Treat deletion as structural: `delete_node` also removes attached links.

4. Let CLDMaker handle geometry.
   - Let a from-scratch `batch_create` invoke automatic layout.
   - Call `layout_diagram` after piecemeal construction or when repairing an older layout.
   - Call layout before adding loop annotations.
   - Use `move_node` only for an intentional final nudge requested by the user.

5. Annotate meaningful feedback.
   - Trace a directed closed cycle and pass each node id once, in cycle order, to `annotate_loop`.
   - Provide a short mechanism title, a plain-language causal rationale, and supporting source titles with stable URLs when research informed the loop.
   - Let CLDMaker validate closure, derive reinforcing or balancing polarity, number the loop, and place the marker and comment.
   - Annotate distinct mechanisms rather than every mathematically possible composite cycle.

6. Verify and save.
   - Call `read_state` after structural edits.
   - Confirm that every intended node and link exists, every polarity matches the causal claim, and every annotated node sequence is a valid directed cycle.
   - Call `save_diagram` after meaningful progress or whenever the user requests a saved artifact.
   - Report the saved path and summarize the annotated loops.

## Research-derived diagrams

Use the `cld-research-to-diagram` skill before authoring when the structure must be inferred from sources. Keep evidence and interpretation visible in the diagram rather than presenting the finished graph as self-justifying.

## Completion criteria

Finish only when the saved diagram matches the verified state, meaningful loops have explanatory annotations, and uncertainties or locally contingent links are explicit in the user-facing analysis.
