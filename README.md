# Inverted Encoding Model(IEM)

### [related papers]
* Oh, B. I., Kim, Y. J., & Kang, M. S. (2019). Ensemble representations reveal distinct neural coding of visual working memory. Nature communications, 10(1), 1-12.<br>
* Yu, Q., & Shim, W. M. (2019). Temporal-order-based attentional priority modulates mnemonic representations in parietal and frontal cortices. Cerebral Cortex, 29(7), 3182-3192.<br>

### [underlying mathematical concepts]
The IEM re-construct the stimuli as a weighted sum of hypothesized channels.<br>
__Information below came from Yu & Shim (2019).__<br>
* Baseline from each voxel's response: $B=B-m(m^TB)$
  * $B$: data matrix from each run, v\*c
    - __v__: the number of voxels in the ROI
    - __c__: the number of features 
  * __m__: mean response across all stimulus condition for each voxels
* $W$ (weight matrix)
  * project hypothesized channel response to actual measured fMRI signal in training dataset &rarr; use __weight matrix__ &rarr; extract estimated channel response for test datset
  * $B_1 = WC_1$
    * $B_1$: training dataset
    * $C_1$: hypothesized channel response
  * least-squared estimate
    * use linear regression
    * $\widehat{W} = B_1 {C_1}^T(C_1 {C_1}^T)^{-1}$
    * $\widehat{C_2} = (\widehat{W}^T \widehat{W})^{-1}\widehat{W}^TB_2$ &rarr; estimated channel response
