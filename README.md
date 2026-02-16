Minimal obstruction: (a) Gödel’s First Incompleteness Theorem

Proof Outline:

1. **Identification of the Logically Minimal Theorem T:**  
   T is Gödel’s First Incompleteness Theorem (1931), which states that for any consistent, recursively axiomatizable theory S extending PA, there exists a sentence G in the language of S such that S does not prove G, and if S is ω-consistent, G is true in the standard model ℕ. This theorem establishes the existence of true-but-unprovable sentences, which is necessary for the undecidability and Π¹₁-classification of Σ.

2. **Definition of Σ:**  
   Σ = { ⟨e⟩ : program e outputs a sentence φ such that  
         (i) φ is true in the standard model ℕ, and  
         (ii) S ⊬ φ }.

3. **Proof that T ⇒ Σ is undecidable, non-r.e., and Π¹₁-complete:**  
   - By T, S has a true-in-ℕ but unprovable sentence G_S. Construct e_G such that e_G outputs G_S. Then ⟨e_G⟩ ∈ Σ.  
   - **Undecidability:** Deciding Σ requires determining whether φ output by e is both true in ℕ and unprovable in S. By T, unprovable truths exist and are syntactically undecidable, so Σ is undecidable.  
   - **Non-r.e.:** Enumerating Σ requires listing true-but-unprovable sentences. Since the set of true sentences is not recursively enumerable for syntactic reasons (diagonalization in Gödel, 1931), Σ is not r.e.  
   - **Π¹₁-completeness:** Membership involves a universal second-order quantifier over proofs or models of S. Reduction from known Π¹₁-complete problems (e.g., complement of true Π¹₁⁰ sentences) is possible via encoding into output sentences of e, establishing Π¹₁-hardness. Membership follows from the universal quantification inherent in the definition.

4. **Explicit Many-One Reduction from the Halting Problem to Σ:**  
   - Let H = { ⟨p, x⟩ : program p halts on input x }.  
   - Construct e_{p,x} as follows:  
     1. e_{p,x} simulates p on x.  
     2. If p halts, e_{p,x} outputs the Gödel sentence G_S conjoined with “p halts on x”.  
     3. If p does not halt, e_{p,x} outputs a contradiction (e.g., “0=1”).  
   - Then ⟨e_{p,x}⟩ ∈ Σ iff p halts on x and the output is true-but-unprovable in S.  
   - This shows H ≤_m Σ via computable reduction, embedding halting into the Σ-membership problem.  
   - Conversely, Σ cannot be reduced to H, as determining Σ membership requires checking truth in ℕ, which is not computable even with an H-oracle.

5. **Proof that ¬T ⇒ the conclusions fail:**  
   - Assume ¬T: S is complete. Then for any e outputting φ, S ⊢ φ or S ⊢ ¬φ. No φ can satisfy both (i) true-in-ℕ and (ii) unprovable in S. Hence Σ = ∅, which is decidable, r.e., and not Π¹₁-complete.

6. **Classification for Each Unchosen Theorem U:**  
   - (b) Gödel’s Second Incompleteness Theorem: Derivable from T. Uses fixed-point lemma on S’s consistency; strictly secondary.  
   - (c) Tarski’s Undefinability of Truth: Independent of T. Shows truth in ℕ cannot be defined internally, but T relies only on ω-consistency to establish incompleteness.  
   - (d) Rice’s Theorem: Independent of T. Applies to arbitrary non-trivial program properties; does not depend on arithmetic incompleteness.  
   - (e) Löb’s Theorem: Derivable from T. Uses provability predicates from T’s construction; secondary.

7. **Presupposition of External Truth in Gödel I:**  
   - Gödel I presupposes an external notion of truth in ℕ to assert that the Gödel sentence G_S is true but unprovable.  
   - This does **not** make it logically dependent on Tarski for classifying Σ, as T relies on ω-consistency (syntactic property) alone. Tarski provides broader context but is not required for Σ’s Π¹₁-classification.

8. **Conclusion:**  
   - Minimal obstruction for Σ’s undecidability, non-r.e., and Π¹₁-completeness is Gödel’s First Incompleteness Theorem.  
   - Halting Problem reduction demonstrates Σ is computationally at least as hard as H, embedding classical undecidability within arithmetic self-reference.  
   - All other theorems are either derivable or independent, preserving the logical minimality of T.
