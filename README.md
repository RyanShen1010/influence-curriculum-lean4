# influence-curriculum-lean4
We present a data-centric study of automated theorem proving in Lean 4, using influence functions
to quantify the contribution of individual training examples and systematically comparing data pruning
and curriculum learning strategies. We fine-tune a Qwen2.5-0.5B-Instruct model with QLoRA on 8,497
theorem–proof pairs from the NuminaMath-LEAN dataset and compute per-sample influence scores
via the DataInf diagonal approximation. Based on these scores, we evaluate 19 strategies spanning
three families: traditional curriculum learning, influence-based curriculum ordering, and data pruning,
on the MiniF2F benchmark. Our results reveal three principal findings. First, the absolute-influence
descending curriculum (Abs Influence Desc), which prioritizes training samples by the magnitude of
their influence scores regardless of sign, achieves the best overall performance: pass@1 = 4.58% and
pass@8 = 16.67%, representing a 5→ improvement in pass@8 over the default baseline (3.33%). Second,
among traditional curriculum strategies, the easy-to-hard ordering attains the strongest results (pass@1
= 3.33%, pass@8 = 10.00%), outperforming random shuffling by approximately 4→ in pass@1 and
1.5→ in pass@8, and confirming the benefit of progressive difficulty scheduling. Third, data pruning is
consistently counterproductive: all five pruning strategies either match or underperform the no-pruning
baseline (pass@1 ↑ 0.83%), demonstrating that data diversity is more important than data purity for
theorem proving. Correlation analysis reveals that proof length is the strongest predictor of influence
(Spearman ω = 0.474), and that helpful samples are on average 7→ longer than harmful ones. These
findings validate influence functions as a practical tool for data selection and underscore the primacy of
data ordering over data removal in formal reasoning tasks.
