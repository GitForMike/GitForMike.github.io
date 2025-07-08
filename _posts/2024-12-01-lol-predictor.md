---
title: Predicting League of Legends Win Rates with Champion Compositions
---

I'm excited to introduce my latest project: a website that predicts win rates in League of Legends based on champion compositions. 
Check out my project: **[https://mike.hndblog.com/lol/](https://mike.hndblog.com/lol/)**


This project combines my interest in League of Legends with my passion for machine learning and web development. I wanted to create a tool that could provide insights into how different champion combinations might perform in a match.

## Key Features

*   **Win Rate Prediction:** The core feature is the ability to predict the win rate of a given champion composition. By selecting champions for each team, the website uses a trained machine learning model to estimate the likelihood of each team winning.
*   **Intuitive User Interface:** The website provides a simple and easy-to-use interface for selecting champions and viewing predictions.

## Technologies Used

This project utilizes the following technologies:

*   **Next.js:** A React framework for building server-side rendered and statically generated web applications, providing excellent performance and SEO.
*   **TensorFlow.js:** A JavaScript library for machine learning in the browser. This allowed me to train and deploy the prediction model directly on the client-side.
*   **League of Legends Match Data API:** I used a Riot Games API to gather historical match data, which was crucial for training the machine learning model.

## How it Works

1.  **Data Collection:** I collected a large dataset of League of Legends match data from a public API. This data included information about the champions picked for each team and the outcome of the match.
2.  **Model Training:** I used TensorFlow.js to train a machine learning model(Auto ML) on this dataset. The model learned to identify patterns in champion compositions and correlate them with win rates. 
3.  **Prediction:** When a user selects a champion composition on the website, the trained model makes a prediction about the win rate for each team.

## Future Plans

I plan to continue improving this project by:

*   Improving the accuracy of the prediction model by using more data and exploring different model architectures.
*   Adding more features, such as champion statistics and team synergy analysis.
*   Improving the user interface and user experience.

I welcome any feedback or suggestions you may have! Please feel free to explore the website and let me know what you think.

Thank you for your interest!