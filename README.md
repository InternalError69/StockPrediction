<div align="center">
  <h1>📈 StockPrediction</h1>
  <p>
    <strong>StockPrediction</strong> is an interactive machine learning pipeline designed to forecast stock market trends using historical financial data. Leveraging the Yahoo Finance API (<code>yfinance</code>) and Scikit-Learn's Random Forest classification, the model predicts the likelihood of a stock's closing price increasing the following day.
  </p>
</div>

<hr>

<h2>✨ Key Features</h2>
<ul>
  <li><strong>Automated Data Ingestion:</strong> Directly fetches maximum historical market data (e.g., Nifty 500) using the <code>yfinance</code> API for completely up-to-date training sets.</li>
  <li><strong>Predictive Analytics:</strong> Uses a <strong>Random Forest Classifier</strong> to identify non-linear patterns in financial indicators to predict directional market movement (Target: 1 for up, 0 for down).</li>
  <li><strong>Feature Engineering:</strong> Cleans and processes raw market data (Open, High, Low, Close, Volume) by building forward-shifted sequences and removing non-impactful metadata.</li>
  <li><strong>Robust Backtesting:</strong> Implements <code>min_samples_split=100</code> to inherently prevent the model from overfitting to market noise, a common issue in financial machine learning.</li>
</ul>

<hr>

<h2>🛠 Tech Stack</h2>
<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Tools</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Machine Learning</strong></td>
      <td>
        <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat&logo=scikit-learn&logoColor=white" alt="Scikit-Learn">
      </td>
    </tr>
    <tr>
      <td><strong>Data Engineering</strong></td>
      <td>
        <img src="https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white" alt="Pandas">
        <img src="https://img.shields.io/badge/yfinance-00A9E0?style=flat&logo=yahoo&logoColor=white" alt="Yahoo Finance">
      </td>
    </tr>
    <tr>
      <td><strong>Visualization</strong></td>
      <td>
        <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=flat&logo=Matplotlib&logoColor=black" alt="Matplotlib">
      </td>
    </tr>
    <tr>
      <td><strong>Environment</strong></td>
      <td>
        <img src="https://img.shields.io/badge/Jupyter-%23F37626.svg?style=flat&logo=Jupyter&logoColor=white" alt="Jupyter Notebook">
      </td>
    </tr>
  </tbody>
</table>

<hr>

<h2>🚀 Getting Started</h2>

<h3>Prerequisites</h3>
<ul>
  <li>Python 3.8+</li>
  <li>Jupyter Notebook</li>
</ul>

<h3>Installation & Launch</h3>
<ol>
  <li>
    <strong>Clone the Repo</strong>
<pre><code>git clone https://github.com/internalerror69/stockprediction.git
cd stockprediction</code></pre>
  </li>
  <li>
    <strong>Install Dependencies</strong>
<pre><code>pip install yfinance scikit-learn pandas matplotlib jupyter</code></pre>
  </li>
  <li>
    <strong>Launch the Notebook</strong>
<pre><code>jupyter notebook StockPricePred.ipynb</code></pre>
  </li>
</ol>

<hr>

<h2>📊 How It Works</h2>
<p>The system predicts directional stock momentum using the following pipeline:</p>
<ol>
  <li><strong>Data Retrieval:</strong> Connects to Yahoo Finance to download the daily Open, High, Low, Close, and Volume histories for target indexes (e.g., ^CRSLDX for Nifty 500).</li>
  <li><strong>Data Cleansing:</strong> Filters out irrelevant columns (Dividends, Stock Splits) and drops pre-2011 data to focus the model on modern market behaviors.</li>
  <li><strong>Target Creation:</strong> Generates a "NextDay" closing price column and maps it to a binary <code>Target</code> (1 if tomorrow's Close > today's Close, else 0).</li>
  <li><strong>Training:</strong> The dataset is split sequentially (maintaining chronological order) into a training set and a testing set (the last 100 days).</li>
  <li><strong>Modeling:</strong> A <code>RandomForestClassifier</code> fits on the "Close", "Volume", "Open", "High", and "Low" predictors. A defined <code>random_state</code> ensures reproducible outcomes during evaluations.</li>
</ol>

<hr>

<h2>📁 Repository Highlights</h2>
<ul>
  <li><code>StockPricePred.ipynb</code>: The core Jupyter Notebook containing the end-to-end logic—from API calls and feature engineering to the Random Forest model training logic.</li>
  <li><code>README.md</code>: Project documentation and setup guide.</li>
</ul>

<hr>

<p align="center">
  <small>MIT License &copy; 2026</small>
</p>
