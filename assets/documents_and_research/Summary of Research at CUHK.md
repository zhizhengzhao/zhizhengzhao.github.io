# Research Summary: Completing the Symmetry Group in Crystal Structure Prediction

**Author:** Zhizheng Zhao

## 1. Project Abstract

This project addresses a fundamental theoretical deficiency in state-of-the-art Crystal Structure Prediction (CSP) models, specifically **DiffCSP**. While existing frameworks successfully incorporate $E(3)$ **equivariance** (handling rotation and translation), they fail to account for the **infinite discrete symmetry** arising from unit cell basis transformations ($GL(3, \mathbb{Z})$). This renders the theoretical framework incomplete.

To achieve **theoretical closure**, I proposed a **Niggli-Augmented Framework**. By utilizing the Niggli Reduction algorithm as a canonical mapping tool, I designed a novel **"Niggli Proxy Loss"**. This loss function resolves the inherent non-differentiability of the reduction algorithm by decoupling target alignment from gradient computation, effectively bridging the gap between discrete crystallographic definitions and continuous deep learning optimization.

## 2. Theoretical Motivation: The Missing Symmetry Group

The physical equivalence of a crystal structure is governed by a composite symmetry group. Current models only capture a subset of this manifold.

### 2.1 The Solved: Euclidean Symmetry $E(3)$

Existing models like DiffCSP are built on $E(3)$-equivariant Graph Neural Networks. They successfully handle:

- **External Rotation (**$SO(3)$**):** $\mathbf{L}' = \mathbf{Q}\mathbf{L}$, where $\mathbf{Q}$ is a rotation matrix.
- **Periodic Translation (**$T(3)$**):** Shifts in atomic coordinates under periodic boundary conditions.
- **Status:** **Resolved.** The model naturally generalizes across these transformations.

### 2.2 The Unresolved: Lattice Basis Invariance

The core limitation identified in this research is the **Basis Transformation Group**. A single infinite crystal lattice can be described by infinitely many equivalent unit cells (bases).

- **Transformation:** $\mathbf{L}' = \mathbf{L}\mathbf{M}$, where $\mathbf{M} \in GL(3, \mathbb{Z})$ (unimodular integer matrix).
- **The Gap:** Standard equivariant features are invariant to rotation ($\mathbf{Q}$) but **sensitive** to basis choice ($\mathbf{M}$). DiffCSP implicitly assumes a specific, standardized basis (often from a database), meaning it learns a "one-to-one" mapping rather than the physically correct "one-to-many" manifold. This limits the model's robustness and physical validity.

## 3. Methodology: Niggli-Augmented Framework

To enforce invariance to basis transformations, I integrated **Niggli Reduction (**$\mathcal{N}$**)**—a crystallographic algorithm that maps any lattice to a unique, canonical representation ($\mathbf{L}_{\text{niggli}}$).

### 3.1 The Challenge: Non-Differentiability

The Niggli reduction $\mathcal{N}$ is an iterative, discrete algorithm. Directly applying it to the model's prediction breaks the computation graph:

$$\mathcal{L} = \text{MSE}(\mathcal{N}(\mathbf{L}_{\text{pred}}), \mathbf{L}_{\text{canonical}}) \quad \Rightarrow \quad \nabla \mathcal{L} \text{ is undefined.}$$

### 3.2 The Solution: Niggli Proxy Loss

I designed a **Proxy Loss** mechanism that turns the Niggli algorithm from a computational block into a "target alignment guide." Instead of differentiating *through* the algorithm, we use it to find the optimal basis for the ground truth.

**Workflow:**

1. **Basis Identification:** Compute the transformation matrix $\mathbf{N}_{\text{pred}}$ that maps the *predicted* lattice to its Niggli form.

   $$(\_, \mathbf{N}_{\text{pred}}) = \text{NiggliReduce}(\mathbf{L}_{\text{pred}}.\text{detach()})$$

2. **Target Alignment (The Proxy):** Instead of forcing the prediction to match the canonical label directly, we apply the **inverse** transformation ($\mathbf{M} = \mathbf{N}_{\text{pred}}^{-1}$) to the *canonical ground truth*. This projects the ground truth into the *prediction's current basis*.

   $$\mathbf{L}'_{\text{target}} = \mathbf{L}_{\text{canonical}} \cdot \mathbf{M}$$

3. **Differentiable Optimization:** We calculate the MSE between the prediction and this aligned proxy target.

   $$\mathcal{L} = \text{MSE}(\mathbf{L}_{\text{pred}}, \mathbf{L}'_{\text{target}})$$

**Outcome:** This allows PyTorch gradients to flow naturally through $\mathbf{L}_{\text{pred}}$ while mathematically enforcing that the model is penalized only for physical shape errors, not for choosing a mathematically equivalent but different basis.

## 4. Preliminary Findings

Experiments on a simplified MLP architecture validated the mathematical correctness of the Proxy Loss—the model successfully learned to predict physically valid structures regardless of the basis representation.

However, a practical engineering bottleneck was identified: **Pathological Lattices**. In early training stages, the model outputs highly distorted or near-singular matrices. Standard crystallographic libraries (e.g., `spglib`) are not robust to these non-physical inputs, leading to convergence failures in the Niggli algorithm.