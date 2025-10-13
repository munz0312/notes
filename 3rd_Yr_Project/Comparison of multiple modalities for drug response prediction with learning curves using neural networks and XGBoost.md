Learning curves - plotting the performance on unseen data (a.k.a generalisation error) over different values of training set sizes, n.

We can use them to estimate how the performance of machine learning models on drug response predictions improves with the collection of more data.

Multiple studies have shown that NNs outperform other machine learning algorithms for DRP (Chang et al 2018, Sakellaropoulos et al 2019, Liu et al. 2020, 2022, Zhu et al. 2021).
May be because drugs are represented by unstructured data, NNs are good with this.

3 regions in a typical learning curve:
1). Small data region - poor performance due to insufficient data
2). The power-law region. The model performance follows a power-law equation where increasing data increases performance
3). Diminishing returns region. Adding more data does improve model performance but at a slower rate than 2.

Learning curves can be a powerful tool - they can tell us the model's potential to improve when additional data is given by extrapolating the curve.

Used two datasets - a small one (38) and a big one (877)
![[Pasted image 20251013203404.png]]

For smaller dataset, NN was better, for larger, XGBoost was better.

![[Pasted image 20251013203512.png]]

