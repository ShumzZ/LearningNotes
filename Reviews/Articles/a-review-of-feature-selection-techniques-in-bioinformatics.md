[pdf](https://watermark.silverchair.com/btm344.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAnYwggJyBgkqhkiG9w0BBwagggJjMIICXwIBADCCAlgGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMgwDm-grtZfRtl8DbAgEQgIICKeesj_Ap8R26R8Z18iZ6a9bh08STWEKwlHOftyaCFPAgKjeiIpjbvUSdJBDnjuquVK-JlH0hhM6RIMC3BJSNA7jHJ_ltcl_r9MgghSNS1PujfO247a4mH7s6pK-TZ6lq4PCEaYhFWZ8OKXfH_K_rR_17-vIsnQUmKh5z1Zt8YZpQ4ojt8AoRTnciySEP6VW__PlCzCTusydwzSy3F-jwE0MciR17bXMmXpHmnEzeR0YGXm5CmeRrLzB64MHYXB_OSSXDBSfayeWxG_orrDcJWcNXPKKVXWkcy9EGTjFamSe2SA4GlVbDZ3gn_cdOZbyERA88RfeMWgnhGU-TZhV_PmImBxtBlhS1ZiAWewTIyLUsV3sdewbZESqoXxoLQ5Yf4W_dt2XKyNPYlfByHaRRzQ12tClF79FXO3_jRSUHsTbJKfwio-byvTGcbkPmB6SdD83SUZvOUKR0bhi5egwNPHzJXEzcFk4vzlrDGxuRM9arvHKAen131Ab38QM1bvY8B-bMVqOefkocuQUsWb-cWh5mY0LZjhI8w_L_tGq8vCpBd5ztnUALti6jYwhkLNa8BshmYTw-BqvHqL6qlHxyWHbD52jHQQHZTgxSJGk9JNzc1BocOdOyfKilZIvyuRfStxgLWtezh8a7CRlyethITg_BOzSz2-3qqWOHYIMCkUR7PqacB3JGQQjZeLFZ19Ge1wpx6wv7IFm34Qcxh0NU_7sC0Pzy-Wt8_0o)
Vol. 23 no. 19 2007, pages 2507–2517 BIOINFORMATICS REVIEW doi:10.1093/bioinformatics/btm344

- general type of feature selection:
  - based on projection: PCA
  - based on compression: using information theory
  - do not alter original representation, only select a subset of the features, preserving the semantics of the variable and thus interpretability
- This paper only focuses on FS in classification problems and FS techniques fall into three categories: Filter, Wrapper and Embedded


|Method|Idea|Pro|Con|Examples|
|--|--|--|--|--|
|Filter|only look at intrinsic properties of features/its relationship with target|fast, scalable, independent of classifier|ignore feature dependencies in univariate case, ignores the interaction with the classifier(search in feature subset space is separate from the search in hypothesis space)|Chi-square, Information Gain, Gain ratio, Correlation based FS, variance threshold|
|Wrapper|embed model hypothesis search within feature subset search, i.e. for each possible feature subset, find the optimal classifier by training and cross-validation; further divided into deterministic and randomized approaches|take into consideration the interactions between feature subset search and model selection, and dependencies between features | computationally intense; higher risk of overfitting; stuck at local optimal|Sequential forward/backward selection (SFS/SBS), randomized hill climbing, genetics algorithms
|Embedded|feature subset search is built into classifier construction, essentially searching in the combined space of feature subsets and model hypotheses|wrapper's advantages + less computationally intense|only apply to certain learning algorithms| decision tree; logistic regression L1 regularization


see also:
- https://sebastianraschka.com/faq/docs/feature_sele_categories.html
- https://medium.com/@cxu24/common-methods-for-feature-selection-you-should-know-2346847fdf31
