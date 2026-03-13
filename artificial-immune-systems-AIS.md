# Artificial Immune Systems (AIS)

A submodule of the [ml-algorithm-dataset](https://github.com/ronniross/ml-algorithm-dataset) repository.

## Introduction 
In computer science and machine learning, algorithms inspired by the biological immune system are collectively known as **Artificial Immune Systems (AIS)**. 

Because researchers constantly create minor tweaks and hybridize algorithms, it is impossible to list literally *every* single variant ever published in an academic paper. However, AIS is strictly divided into **four major paradigms** based on the biological theories that inspired them. 

But here is a comprehensive list of all the fundamental AIS algorithms, along with their most notable variants, categorized by their biological inspiration.

---

### 1. Clonal Selection Algorithms (CSA)
**Biological Inspiration:** The Clonal Selection Theory (how B-cells and T-cells mutate and clone themselves to destroy a specific, recognized pathogen). 
**Primary Use:** Optimization (both continuous and combinatorial) and pattern recognition.

*   **CLONALG (Clonal Selection Algorithm):** The most famous AIS algorithm, developed by de Castro and Von Zuben. It uses cloning, hypermutation, and receptor editing to solve optimization and pattern recognition tasks.
*   **BCA (B-Cell Algorithm):** Focuses heavily on the somatic hypermutation process of B-cells. Used primarily for continuous optimization.
*   **opt-IA (Optimization Immune Algorithm):** A variant of CLONALG designed specifically for numerical optimization, featuring static cloning and inversely proportional hypermutation.
*   **Mopt-IA:** The multi-objective version of opt-IA, used when a problem has multiple competing goals.
*   **Immunos:** A family of algorithms (Immunos-1, Immunos-2, Immunos-81, Immunos-99) used primarily for data classification.
*   **CSA-DE (Clonal Selection Algorithm with Differential Evolution):** A hybrid that borrows mutation strategies from Differential Evolution to improve search capabilities.
*   **ICSA (Improved Clonal Selection Algorithm):** Various implementations exist under this name, usually incorporating adaptive mutation rates.

### 2. Negative Selection Algorithms (NSA)
**Biological Inspiration:** The maturation process of T-cells in the thymus, where T-cells that attack the body's own cells (self) are destroyed, leaving only cells that attack anomalies (non-self).
**Primary Use:** Anomaly detection, fault detection, and cybersecurity (intrusion detection).

*   **Standard NSA (Negative Selection Algorithm):** The original algorithm by Stephanie Forrest. It generates random "detectors" (strings of data). If a detector matches normal data ("self"), it is discarded. The surviving detectors are used to monitor for anomalies ("non-self").
*   **RNSA (Real-valued Negative Selection Algorithm):** Adapts the original string-matching NSA to work with continuous, real-valued numerical data using distance metrics (like Euclidean distance).
*   **V-Detector (Variable-size Detector):** A major improvement on RNSA. Instead of all anomaly detectors being the same size, it generates detectors of varying sizes to cover the "non-self" space much more efficiently without overlapping the "self" space.
*   **MILA (Multilevel Immune Learning Algorithm):** Combines negative selection with other immune concepts for anomaly detection.
*   **Positive Selection Algorithm:** The conceptual opposite of NSA. Detectors are generated and kept *only* if they match "self." It is used for monitoring system stability rather than hunting for anomalies.
*   **Grid-based NSA:** Divides the problem space into a grid to speed up the generation of detectors.

### 3. Artificial Immune Networks (AIN / aiNet)
**Biological Inspiration:** Jerne’s Immune Network Theory, which suggests that immune cells do not just react to pathogens, but also interact with, stimulate, and suppress *each other* to maintain a dynamic memory of the environment.
**Primary Use:** Data clustering, data visualization, and dynamic optimization.

*   **AINE (Artificial Immune Network):** One of the earliest network models (by Hunt and Cooke). Cells stimulate each other if they are similar, and suppress each other if they are too similar (to prevent redundancy).
*   **RLAIS (Resource Limited Artificial Immune System):** An evolution of AINE introduced by Timmis. It introduces the concept of a limited pool of "resources" (like B-cell counts) to control the uncontrolled growth of the network.
*   **aiNet (Artificial Immune Network for Data Analysis):** Developed by de Castro and Von Zuben. Used heavily for clustering and filtering redundant data.
*   **opt-aiNet:** An adaptation of aiNet for multimodal optimization (finding multiple global and local optimal solutions simultaneously).
*   **dopt-aiNet:** "Dynamic" opt-aiNet. Designed for optimization in environments where the optimal solution changes over time.
*   **SSAIS (Self-Stabilizing AIS):** A network algorithm designed to maintain a stable state in constantly changing data streams.
*   **SIA (Supervised Immune Algorithm):** A network-based algorithm adapted for supervised machine learning and classification.

### 4. Danger Theory & Dendritic Cell Algorithms (DCA)
**Biological Inspiration:** Matzinger’s Danger Theory, which proposes that the immune system does not just distinguish between "self" and "non-self," but rather reacts to "danger signals" emitted by injured or dying cells. Dendritic cells are the agents that collect these signals.
**Primary Use:** Real-time anomaly detection, intrusion detection systems (IDS), and malware detection.

*   **DCA (Dendritic Cell Algorithm):** The foundational algorithm by Greensmith and Aickelin. It processes combinations of signals (Pathogen-Associated Molecular Patterns (PAMPs), Danger Signals, Safe Signals) to determine if a specific process or data point is anomalous.
*   **dDCA (Deterministic Dendritic Cell Algorithm):** A streamlined, less randomized version of the standard DCA that requires less computational power and yields consistent, repeatable results.
*   **TLR (Toll-Like Receptor) Algorithm:** Focuses on the pattern-recognition receptors found on dendritic cells. Often used alongside DCA to improve signal processing.
*   **cnsDCA (Cellular Negative Selection Dendritic Cell Algorithm):** A hybrid approach combining the signal-processing of DCA with the detector-generation of NSA.

### 5. Hybrid Immune Algorithms
Because AIS algorithms are highly adaptable, they are frequently merged with other Artificial Intelligence paradigms.

*   **IGA (Immune Genetic Algorithm):** Combines Genetic Algorithms (GA) with immune concepts. It uses "vaccines" (prior knowledge about the problem) to prevent the genetic algorithm from degrading during mutation.
*   **Quantum-inspired Immune Algorithms (QIA):** Utilizes principles of quantum computing (like qubits and superposition) to represent antibodies, drastically increasing the speed of the Clonal Selection process.
*   **Neuro-Immune Networks:** Combines Artificial Neural Networks (ANNs) with Artificial Immune Networks. The immune network is often used to optimize the weights and topology of the neural network.
*   **Fuzzy AIS:** Integrates Fuzzy Logic to handle uncertainty in the matching processes of Negative Selection Algorithms (e.g., matching a pathogen 80% instead of a strict yes/no).
*   **AIS-PSO (Particle Swarm Optimization):** Uses the hypermutation of immune algorithms to prevent Particle Swarm algorithms from getting stuck in local optima.

### Summary
If you are looking to study or implement AIS, the four algorithms you absolutely must know are **CLONALG** (for optimization), **NSA** (for anomaly detection), **aiNet** (for clustering), and **DCA** (for modern, signal-based anomaly detection). Almost all other algorithms on this list are derivatives of these four.





Here is a formatted list of credible, foundational academic sources for the algorithms mentioned in the previous document. I have organized them by category so you can easily map them to the sections on your first page. 

These are the seminal papers and books that introduced these algorithms to the field of computer science. You can copy and paste this directly into the second page of your Markdown document.

***

## References: Artificial Immune Systems

### General Overviews & Foundational Books

*   **de Castro, L. N., & Timmis, J. (2002).** *Artificial Immune Systems: A New Computational Intelligence Approach.* Springer-Verlag. 
    > *Note: This is considered the "bible" of AIS and covers the biological theory alongside algorithmic implementations.*
*   **Dasgupta, D. (Ed.). (1999).** *Artificial Immune Systems and Their Applications.* Springer.
    > *Note: An excellent collection of early applications of AIS across various domains.*

### 1. Clonal Selection Algorithms (CSA)
*   **Original CLONALG:** de Castro, L. N., & Von Zuben, F. J. (2002). Learning and optimization using the clonal selection principle. *IEEE Transactions on Evolutionary Computation*, 6(3), 239-251.
*   **BCA (B-Cell Algorithm):** Kelsey, J., & Timmis, J. (2003). Immune inspired somatic contiguous hypermutation for function optimisation. *Genetic and Evolutionary Computation Conference (GECCO)*, 207-218.
*   **opt-IA (Optimization Immune Algorithm):** Cutello, V., Nicosia, G., & Pavone, M. (2004). A real coded clonal selection algorithm for global optimization using a fundamentally new mutation operator. *Proceedings of the 2004 ACM Symposium on Applied Computing*, 95-100.

### 2. Negative Selection Algorithms (NSA)
*   **Standard NSA:** Forrest, S., Perelson, A. S., Allen, L., & Cherukuri, R. (1994). Self-nonself discrimination in a computer. *Proceedings of 1994 IEEE Computer Society Symposium on Research in Security and Privacy*, 202-212.
    > *Note: This is the seminal paper by Stephanie Forrest that birthed the anomaly detection branch of AIS.*
*   **V-Detector / RNSA:** Ji, Z., & Dasgupta, D. (2007). Revisiting negative selection algorithms. *Evolutionary Computation*, 15(2), 223-251.
    > *Note: The primary paper introducing variable-sized detectors to solve the scaling problems of the original NSA.*

### 3. Artificial Immune Networks (AIN / aiNet)
*   **AINE (Original Network Model):** Hunt, J. E., & Cooke, D. E. (1996). Learning using an artificial immune system. *Journal of Network and Computer Applications*, 19(2), 189-212.
*   **aiNet (Data Clustering):** de Castro, L. N., & Von Zuben, F. J. (2000). An evolutionary immune network for data clustering. *Proceedings of the Sixth Brazilian Symposium on Neural Networks*, 84-89.
*   **opt-aiNet (Multimodal Optimization):** de Castro, L. N., & Timmis, J. (2002). An artificial immune network for multimodal function optimization. *Proceedings of the 2002 Congress on Evolutionary Computation (CEC)*, 1, 699-704.

### 4. Danger Theory & Dendritic Cell Algorithms (DCA)
*   **Biological Inspiration:** Matzinger, P. (1994). Tolerance, danger, and the extended family. *Annual Review of Immunology*, 12(1), 991-1045.
    > *Note: This is the biology paper by Polly Matzinger that proposed Danger Theory, sparking the creation of the DCA.*
*   **Original DCA:** Greensmith, J., Aickelin, U., & Twycross, S. (2006). Articulation and clarification of the dendritic cell algorithm. *International Conference on Artificial Immune Systems (ICARIS)*, 404-417. Springer.
*   **Deterministic DCA (dDCA):** Greensmith, J., & Aickelin, U. (2008). The deterministic dendritic cell algorithm. *International Conference on Artificial Immune Systems (ICARIS)*, 291-302. Springer.

### 5. Notable Hybrid Algorithms
*   **Immune Genetic Algorithm (IGA):** Jiao, L., & Wang, L. (2000). A novel genetic algorithm based on immunity. *IEEE Transactions on Systems, Man, and Cybernetics-Part A: Systems and Humans*, 30(5), 552-561.
*   **Quantum-inspired Immune Algorithms (QIA):** Dong, N., Wu, C., & Zhang, Y. (2004). Quantum-inspired immune algorithm. *Proceedings of the 2004 Congress on Evolutionary Computation (CEC)*, 2, 2266-2270.


  [1](https://arxiv.org/abs/0910.4903)
  [2](https://dergipark.org.tr/tr/pub/uumfd/336407.xml)
  [3](https://kar.kent.ac.uk/13942/)
  [4](https://ieeexplore.ieee.org/document/10379293/)
  [5](https://ouci.dntb.gov.ua/en/works/lo8xZPE9/)
  [6](https://www.researchgate.net/publication/3418695_Learning_and_Optimization_Using_the_Clonal_Selection_Principle)
  [7](https://www.grafiati.com/en/literature-selections/artificial-immune-systems/book/)
  [8](https://kar.kent.ac.uk/13942/)
  [9](https://pubmed.ncbi.nlm.nih.gov/17535140/)
  [10](https://pmc.ncbi.nlm.nih.gov/articles/PMC3981469/)
  [11](https://www.mdpi.com/2071-1050/14/10/5805)
  [12](https://arxiv.org/pdf/1006.4949)

  ---
  Ronni Ross  
  2026
