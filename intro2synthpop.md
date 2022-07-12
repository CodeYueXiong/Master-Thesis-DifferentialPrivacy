# Evaluating the utility of synthetic datasets

## Overview of possible approaches to be used

- One-way marginals with the `compare()` method
- Two-way marginals using the `utility.tables()` method to visualize the two-way pMSE ratios

In a common sense, the smaller the *pMSE* the higher the analytical validity of the synthetic data. Especailly for the two-way marginals, if all the standardized *pMSE* ratios are below 10, or better still below 3, the utility in this case seems acceptable.
![pMSE explanation](pMSE_explanation.png#center)


### (1). One-way marginals with `compare()`
The generic/general functionality is displayed as follows:
```r
compare(object = data.frame(B3 = syn_dataset_symptoms$B3),
        data = data.frame(B3 = ori_dataset_symptoms$B3),
        vars = c("B3"), cont.na = NULL,
        msel = NULL, stat = "percents", breaks = 20,
        nrow = 2, ncol = 2, rel.size.x = 1,
        utility.stats = c("pMSE", "S_pMSE"),
        cols = c("#1A3C5A","#4187BF"),
        plot = TRUE, table = TRUE)
```

### (2). Two-way marginals with `utility.tables()`
The generic/general functionality is displayed as follows:
```r
utility.twoway <- utility.tables(data = originaldata,
                                 object = syn.object,
                                 plot = TRUE,
                                 table = TRUE)

```

### (3). Using `utility.gen()`
The general function is displayed as follows:
```r
utility.gen(object = syn_data,
            data = bindori_dataset,
            not.synthesised = NULL,
            cont.na = NULL,
            print.stats = c("pMSE", "S_pMSE"))  # do not know why the s_pMSE is quite large
```