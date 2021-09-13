# Scikit-learn

Official: https://scikit-learn.org/stable/modules/svm.html
Good tutorials:
* https://www.datacamp.com/community/tutorials/svm-classification-scikit-learn-python
* https://stackabuse.com/implementing-svm-and-kernel-svm-with-pythons-scikit-learn

Additional libraries: numpy, pandas, matplotlib

## Example steps

With a labeled dataset:
1. Read the dataset `data = pandas.read_csv(pathToDataset)`
    2. `data.shape`
    3. `data.head()`
4. Extract label from features
    * `features = data.drop(labelColumnName, axis=1)`
    * `label = data[labelColumnName]`
6. Split dataset to training and test data
    ```
    from sklearn.model_selection import train_test_split
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.20, random_state=109)
    # random_state -> pick sets at random (109??)
    # test_size??
    ```
7. Train
    ```
    from sklearn.svm import SVC
    svclassifier = SVC(kernel='linear')
    svclassifier.fit(X_train, y_train)
    ```
8. Predicting
    * `y_pred = svclassifier.predict(X_test)`
9. Evaluate
    ```
    from sklearn.metrics import classification_report, confusion_matrix
    print(confusion_matrix(y_test,y_pred))
    print(classification_report(y_test,y_pred))
    ```
10. Example result
```
[[152    0]
 [  1  122]]
              precision   recall   f1-score   support

           0       0.99     1.00       1.00       152
           1       1.00     0.99       1.00       123

avg / total        1.00     1.00       1.00       275
```
## Questions

1. How to turn features into a numerical representation?
    * Probable answer: map each feature to a number (e.g. 1.1.1.1 to 1.0, 1.1.1.2 to 2.0, etc.)
    * **preprocessing.LabelEncoder**

## Scikit: SVM vs SVC
###### source: https://stackoverflow.com/questions/27912872/what-is-the-difference-between-svc-and-svm-in-scikit-learn
They are just different implementations of the same algorithm. The SVM module (SVC, NuSVC, etc) is a wrapper around the libsvm library and supports different kernels while LinearSVC is based on liblinear and only supports a linear kernel. So:
```
SVC(kernel = 'linear')
```
is in theory "equivalent" to:
```
LinearSVC()
```
Because the implementations are different in practice you will get different results, the most important ones being that LinearSVC only supports a linear kernel, is faster and can scale a lot better.

###### tags: `uni`
