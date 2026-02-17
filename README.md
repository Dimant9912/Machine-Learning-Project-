# Machine-Learning-Project-


## 1. Περιγραφή Προβλήματος και Δεδομένων
Για την παρούσα εργασία επιλέχθηκε το **Wine Dataset** από τη βιβλιοθήκη `sklearn`. Πρόκειται για ένα πρόβλημα πολυ-κατηγοριοποίησης (multiclass classification) που αφορά την ταξινόμηση κρασιών με βάση τα χημικά τους χαρακτηριστικά.

* **Δείγματα (Samples):** 178
* **Χαρακτηριστικά (Features):** 13 (π.χ. αλκοόλ, μηλικό οξύ, τέφρα, φλαβονοειδή, κ.λπ.)
* **Κλάσεις (Classes):** 3 διαφορετικοί τύποι κρασιών (0, 1, 2)
* **Προεπεξεργασία:** Έγινε κανονικοποίηση των δεδομένων (StandardScaler) και διαχωρισμός σε Training Set (70%) και Test Set (30%).

---

## 2. Υλοποίηση Μεθόδων και Αποτελέσματα
Όλοι οι αλγόριθμοι υλοποιήθηκαν από το μηδέν (εκτός του MLP όπου χρησιμοποιήθηκε PyTorch), σύμφωνα με τις απαιτήσεις της εκφώνησης.

### 2.1. Principal Component Analysis (PCA)
Υλοποιήθηκε ο αλγόριθμος PCA μέσω υπολογισμού του πίνακα συνδιακύμανσης και ιδιοανάλυσης (eigen-decomposition).
* **Εφαρμογή:** Μείωση των διαστάσεων του training set από 13 σε 5.

### 2.2. Μέθοδος Ελαχίστων Τετραγώνων (Least Squares)
Ο αλγόριθμος προσαρμόστηκε για classification χρησιμοποιώντας One-Hot Encoding για τα labels.
* **Train Accuracy:** 1.0000 (100%)
* **Test Accuracy:** 0.9815 (98.15%)

### 2.3. Λογιστική Παλινδρόμηση (Logistic Regression)
Υλοποιήθηκε με χρήση Stochastic Gradient Descent (SGD) και συνάρτηση κόστους Cross Entropy.
* **Train Accuracy:** 1.0000 (100%)
* **Test Accuracy:** 0.9815 (98.15%)
* *Παρατήρηση:* Κατασκευάστηκε διάγραμμα (plot) της μείωσης του loss ανά epoch.

### 2.4. K-Nearest Neighbors (k-NN)
Υλοποιήθηκε ο υπολογισμός Ευκλείδειας απόστασης χωρίς έτοιμες συναρτήσεις. Δοκιμάστηκαν τιμές του $k$ από 1 έως 10.
* **Βέλτιστο k:** 8
* **Accuracy (k=8):** 0.9815 (98.15%)

### 2.5. Naïve Bayes
Υλοποιήθηκε η Gaussian εκδοχή του αλγορίθμου, υπολογίζοντας μέσες τιμές και διακυμάνσεις για κάθε χαρακτηριστικό ανά κλάση.
* **Train Accuracy:** 0.9758 (97.58%)
* **Test Accuracy:** 1.0000 (100%)

### 2.6. Multilayer Perceptron (MLP)
Υλοποιήθηκε νευρωνικό δίκτυο με χρήση της βιβλιοθήκης **PyTorch**.
* **Αρχιτεκτονική:** Είσοδος (13) -> Linear(64) -> ReLU -> Linear(32) -> ReLU -> Έξοδος (3).
* **Test Accuracy:** 0.9815 (98.15%)
* *Παρατήρηση:* Καταγράφηκε η καμπύλη εκπαίδευσης (Training Loss).

### 2.7. Support Vector Machines (SVM)
Υλοποιήθηκε γραμμικό SVM με την τεχνική One-vs-Rest για την αντιμετώπιση των πολλαπλών κλάσεων, χρησιμοποιώντας Gradient Descent.
* **Test Accuracy:** 0.9815 (98.15%)

### 2.8. K-Means Clustering
Υλοποιήθηκε ο αλγόριθμος συσταδοποίησης από το μηδέν για $k=3$ (όσες και οι κλάσεις).
* **Clustering Accuracy (Purity):** 0.9435 (94.35%)

---


###English Version

## 1. Problem Description and Dataset
For this assignment, the **Wine Dataset** from the `sklearn` library was selected. It presents a multiclass classification problem involving the categorization of wines based on their chemical constituents.

* **Samples:** 178
* **Features:** 13 (e.g., Alcohol, Malic acid, Ash, Flavanoids, etc.)
* **Classes:** 3 distinct wine types (Target 0, 1, 2)
* **Preprocessing:** Data normalization using StandardScaler and splitting into Training Set (70%) and Test Set (30%).

---

## 2. Methodology and Results
All algorithms were implemented from scratch (with the exception of MLP where PyTorch was used), strictly following the assignment requirements.

### 2.1. Principal Component Analysis (PCA)
PCA was implemented via covariance matrix calculation and eigen-decomposition.
* **Application:** Reduced training set dimensionality from 13 to 5 dimensions.

### 2.2. Least Squares Classifier
The algorithm was adapted for classification tasks using One-Hot Encoding for the target labels.
* **Train Accuracy:** 1.0000 (100%)
* **Test Accuracy:** 0.9815 (98.15%)

### 2.3. Logistic Regression
Implemented using Stochastic Gradient Descent (SGD) and Cross Entropy Loss function.
* **Train Accuracy:** 1.0000 (100%)
* **Test Accuracy:** 0.9815 (98.15%)
* *Note:* A plot visualizing the loss reduction per epoch was generated.

### 2.4. K-Nearest Neighbors (k-NN)
Manual implementation of Euclidean distance calculation. Evaluated for $k$ values ranging from 1 to 10.
* **Best k:** 8
* **Accuracy (k=8):** 0.9815 (98.15%)

### 2.5. Naïve Bayes
The Gaussian version of the algorithm was implemented by calculating means and variances for each feature per class.
* **Train Accuracy:** 0.9758 (97.58%)
* **Test Accuracy:** 1.0000 (100%)

### 2.6. Multilayer Perceptron (MLP)
A neural network was implemented using the **PyTorch** framework.
* **Architecture:** Input (13) -> Linear(64) -> ReLU -> Linear(32) -> ReLU -> Output (3).
* **Test Accuracy:** 0.9815 (98.15%)
* *Note:* The training loss curve was recorded and plotted.

### 2.7. Support Vector Machines (SVM)
A linear SVM was implemented using the One-vs-Rest strategy to handle the multiclass nature of the data, optimized via Gradient Descent.
* **Test Accuracy:** 0.9815 (98.15%)

### 2.8. K-Means Clustering
The clustering algorithm was implemented from scratch with $k=3$ (corresponding to the number of ground-truth classes).
* **Clustering Accuracy (Purity):** 0.9435 (94.35%)

---

## 3. Conclusion
All implemented methods achieved exceptionally high accuracy scores (above 94%) on this dataset. The **Naïve Bayes** algorithm achieved the highest performance on the Test Set (100%), while the majority of the other methods (Least Squares, Logistic Regression, k-NN, MLP, SVM) converged to an accuracy of 98.15%.
Όλες οι μέθοδοι πέτυχαν εξαιρετικά υψηλά ποσοστά ακρίβειας (άνω του 94%) στο συγκεκριμένο dataset. Ο αλγόριθμος **Naïve Bayes** σημείωσε την υψηλότερη απόδοση στο Test Set (100%), ενώ οι υπόλοιπες μέθοδοι (Least Squares, Logistic Regression, k-NN, MLP, SVM) συγκλίνανε στο 98.15%.
