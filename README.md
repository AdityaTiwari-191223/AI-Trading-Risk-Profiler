 🚀 AI-Driven Risk Profiling & Reinforcement Learning Trading System






📌 Overview

This repository contains an AI-powered risk profiling and reinforcement learning-based trading system that integrates:

Risk Profiling: Machine learning model to classify users based on financial inputs.

Portfolio Optimization: Implements Modern Portfolio Theory (MPT) and Black-Litterman model.

Reinforcement Learning for Trading: Supports PPO, DQN, and Double DQN for automated trading.

Backtesting & Performance Evaluation: Monte Carlo simulations, Sharpe Ratio, and portfolio backtesting.

📊 Features

📌 User Risk Profiling via AI-based classification

📈 Portfolio Optimization with MPT and Black-Litterman model

🤖 RL-Based Trading Strategies (PPO, DQN, Double DQN)

📉 Backtesting & Sharpe Ratio Analysis

📁 Results Logging for research documentation

🏗️ Folder Structure

📂 AI-Trading-Risk-Profiler
 ┣ 📂 models         # Pre-trained models
 ┣ 📂 data           # Sample datasets
 ┣ 📂 scripts        # Training & evaluation scripts
 ┣ 📂 .github/workflows  # GitHub Actions for automation
 ┣ 📜 main.py        # Streamlit App for UI
 ┣ 📜 README.md      # Project Documentation
 ┣ 📜 requirements.txt  # Dependencies
 ┗ 📜 results.json   # Stored research results

⚡ Installation

# Clone the repository
git clone https://github.com/your-username/AI-Trading-Risk-Profiler.git
cd AI-Trading-Risk-Profiler

# Install dependencies
pip install -r requirements.txt

# Run the Streamlit app
streamlit run main.py

📊 Usage

Run the web app: streamlit run main.py

Select your risk preferences

Choose reinforcement learning model (PPO, DQN, Double DQN)

Get optimized portfolio & trading strategy

View backtesting results & save for research

📊 Generating Sample Results & Plots

To generate sample results and visualizations:

python scripts/generate_visuals.py

This will create updated plots in the assets/ folder.

🔄 Automating Sample Results Commit & Push

To automatically commit and push updated visualizations after running the script, use:

python scripts/generate_visuals.py

git add assets/
git commit -m "Updated sample results and plots"
git push origin main

This ensures your GitHub repository always has the latest results.

🚀 Automating Updates with GitHub Actions

You can set up GitHub Actions to automatically update sample results and commit them to the repository after each run.

1️⃣ Create a GitHub Actions Workflow

Create a file in .github/workflows/update-results.yml with the following content:

name: Auto-Update Sample Results

on:
  push:
    branches:
      - main
  schedule:
    - cron: '0 12 * * *' # Runs every day at 12 PM UTC
  workflow_dispatch: # Allows manual trigger

jobs:
  update-results:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Set Up Python
        uses: actions/setup-python@v3
        with:
          python-version: '3.8'

      - name: Install Dependencies
        run: pip install -r requirements.txt

      - name: Run Sample Visualization Script
        run: python scripts/generate_visuals.py

      - name: Commit and Push Changes
        run: |
          git config --global user.name "github-actions"
          git config --global user.email "github-actions@github.com"
          git add assets/
          git commit -m "Auto-update sample results"
          git push origin main

      - name: Send Email Notification
        uses: dawidd6/action-send-mail@v3
        with:
          server_address: smtp.gmail.com
          server_port: 587
          username: ${{ secrets.EMAIL_USERNAME }}
          password: ${{ secrets.EMAIL_PASSWORD }}
          subject: "GitHub Action: Sample Results Updated"
          body: "The sample results and visualizations have been updated and pushed to the repository."
          to: "your-email@example.com"
          from: "GitHub Actions"

2️⃣ Enable GitHub Actions

Navigate to GitHub Repo → Actions Tab

Click Enable Actions if prompted

3️⃣ Set Up Email Notifications

Go to GitHub Repo → Settings → Secrets and Variables → Actions

Add two secrets:

EMAIL_USERNAME → adityatiwari9205@gmail.com

EMAIL_PASSWORD → Aditya.tiwari191222

4️⃣ Manually Trigger Updates

If needed, manually trigger the workflow from GitHub → Actions → Auto-Update Sample Results → Run Workflow

📈 Sample Results

📊 Portfolio Allocation Visualization



📉 Reinforcement Learning Performance



📊 Backtesting Results



🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.






