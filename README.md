🛡️ DP-Shield: Differential Privacy CSV Anonymizer

A lightweight, zero-dependency, browser-based tool designed to apply Differential Privacy to public datasets. It allows data scientists, NGOs, and researchers to safely publish sensitive tabular data (CSV) by injecting calibrated mathematical noise, protecting individual identities while preserving overall group statistics.

🚀 The Problem: Privacy vs. Utility

When organizations release public data (e.g., healthcare expenses, neighborhood income), simply removing names is not enough. "Anonymized" datasets are highly vulnerable to Data Linkage Attacks, where attackers cross-reference the data with other public records to re-identify individuals.

Differential Privacy solves this by adding random noise to the data. However, adding too much noise destroys the utility of the dataset. This tool demonstrates that trade-off visually.

✨ Features

Zero-Server Architecture: 100% client-side processing. Sensitive CSV data never leaves your computer, ensuring absolute data security.

Interactive Epsilon ($\epsilon$) Tuning: Adjust the "Privacy Budget" via a slider to instantly see the impact on data distortion.

Real-time Visualization: Uses Chart.js to compare the "True" data against the "Differentially Private" data side-by-side.

Statistical Preservation: Automatically tracks the mean (average) of the original data vs. the noisy data to prove that macro-statistics remain accurate.

Safe Export: Download the sanitized CSV, ready for secure public release or AI model training.

🧮 The Math (Laplace Mechanism)

This tool implements the Laplace Mechanism for Differential Privacy.
To protect a numeric column, it calculates the dataset's sensitivity ($\Delta f$) and the user-defined privacy budget ($\epsilon$). It then samples noise from a Laplace distribution:

$$\text{Noise} \sim \text{Laplace}\left(0, \frac{\Delta f}{\epsilon}\right)$$

Low Epsilon (e.g., 0.1): High Privacy, High Noise, Low Data Utility.

High Epsilon (e.g., 5.0): Low Privacy, Low Noise, High Data Utility.

🛠️ How to Use

Since this is a client-side application, there is no complicated backend setup!

Clone this repository or download the source code.

Double-click the csv_anonymizer.html file to open it in any modern web browser.

Upload your CSV file (or use the provided Sample_Community_Survey.csv).

Select the sensitive column you wish to protect (e.g., Annual_Income).

Adjust the Epsilon slider and click Apply Differential Privacy.

View the visual distortion and download the safe CSV.

📁 Project Structure

csv_anonymizer.html - The core application containing all HTML, Tailwind CSS styling, and JavaScript logic.

Sample_Community_Survey.csv - A mock dataset of 20 individuals tracking neighborhood, age, income, and healthcare expenses for testing purposes.

README.md - Project documentation.

🎓 Academic Context

This project was developed as part of a Social Internship focusing on AI Ethics and Data Privacy, specifically addressing the domain of Differential Privacy Frameworks for Public Datasets.
