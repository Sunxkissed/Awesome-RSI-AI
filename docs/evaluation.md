# Evaluating Recursive Self-Improvement

[Back to the resource list](../README.md)

This guide condenses the proposed protocol in Sections 3 and 7 of [Recursive Self-Improvement in AI: A Survey, v1](https://doi.org/10.20944/preprints202609.2680.v1). It is a reporting and experiment-design guide, not a claim that every listed method implements this protocol.

## Separate Three Claims

| Claim | Object being tested | Evidence to collect |
| --- | --- | --- |
| Task gain | The updated solver | Independent task performance under matched inference limits. |
| Retained capability | Persistent solver state | Replay after updates, explicit reset boundaries, regressions, and transfer. |
| Better improvement procedure | The evolved improver | Successors produced from the same held-out starting solvers by the initial and evolved improvers, under matched feedback and cost. |

These claims can coexist. A successful answer revision does not establish retention, and retaining a stronger solver does not establish a stronger improver. A fixed outer algorithm may retain useful adaptive search state; report the actual configuration instead of inferring it from a method name.

## Describe the Configuration

Record the engineering goal, changed objects, retained artifacts, feedback sources, editable components, and fixed anchors. Distinguish the task solver from the update-producing procedure even when they share weights or code. Specify whether a change survives an episode, a new task, a process restart, or a new training run.

Keep three feedback roles separate: information used to propose or train an update, information used to select it, and information used only to audit the final results. Report externally supplied data, tools, tests, and human interventions, including their timing and cost.

## Protect the Evaluation Boundary

1. Declare development tasks, validation tasks, and sealed test tasks before search.
2. Predeclare checkpoint times, budget milestones, stopping rules, and validation-based selection rules.
3. Use validation feedback to accept or reject updates. Specify protected behaviors and allowed regression tolerances.
4. After all runs finish, independently audit the scheduled checkpoints. Do not return audit scores to update generation, acceptance, stopping, or checkpoint selection.
5. Report task and model release dates. A split alone cannot exclude pretraining contamination.

Archive admission, parent selection, and deployment acceptance may follow different rules. A population can retain a weak candidate as a stepping stone without deploying it. Report each decision separately.

## Use Controls That Isolate the Claim

| Comparison | Purpose |
| --- | --- |
| Full loop versus a frozen initial improver | Separates adaptation of the improver from solver updates under a fixed improver. |
| Full loop versus search without persistent updates | Separates inherited changes from additional inference or search. |
| Evolved versus initial improver on copies of identical held-out solvers | Tests downstream update production independently of the main trajectory. |
| Replay and transfer across tasks, models, tools, and feedback sources | Identifies what persists and where the inherited advantage applies. |

Check interface compatibility before swapping improvers. A broken memory schema or tool interface is not evidence of worse improvement ability. When roles are coupled, use the narrowest valid intervention and disclose what cannot be isolated.

## Count the Whole Cost

Track proposal generation, training, validation, and execution without double counting. Include retries, rejected candidates, verifier calls, and environment construction. Report audit cost separately with matched audit-time inference limits.

Use quality-versus-cumulative-cost curves and common cost milestones. A shared budget cap is not equal realized spending, and matching rollout counts does not necessarily match tokens, compute, or monetary cost. Report a resource vector when unlike costs cannot defensibly be converted.

## Report the Trajectory

Include accepted and rejected updates, newly solved tasks, regressions on earlier tasks, retention after resets, uncertainty across repeated searches, recovery cost, and transfer. Separate archive-best, deployed, and final-state curves. A later branch can regress even when an archive preserves a strong candidate.

For infrastructure design, independently rerun produced artifacts and test new tasks or training runs. For repair, test both the target failure and protected behaviors. For automated science, verify reproducibility and the support for scientific claims outside the agent's own reviewer.

The survey reports useful retained changes and limited evidence of improved update production. It does not establish unrestricted or reliably accelerating self-improvement. See its Table 7 for configuration-specific protocol evidence; the rows use different tasks and budgets and should not be treated as a common leaderboard.
