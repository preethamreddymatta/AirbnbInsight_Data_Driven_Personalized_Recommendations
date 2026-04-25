# AirbnbInsight_Data_Driven_Personalized_Recommendations

# Airbnb Recommendation System (Hybrid + Personalized)
## Overview

Finding the right Airbnb listing can be overwhelming due to the sheer number of options across cities, price ranges, and amenities. This project builds a scalable, end-to-end recommendation system that leverages listing metadata and large-scale guest review data to generate personalized and relevant accommodation suggestions.

The system combines content-based filtering, popularity modeling, and hybrid ranking strategies, integrating text, numerical, and categorical features into a unified recommendation pipeline.

## Problem Statement

How can we design a personalized Airbnb recommendation system that effectively combines amenities, pricing, location, and popularity signals to suggest the most relevant properties?

This project addresses:

Personalized recommendations based on user preferences
Feature fusion across multiple data types (text + numeric + categorical)
Ranking optimization using relevance metrics (Precision@K, MAP, nDCG)
## Dataset
Airbnb listings across major global cities
Includes:
Listing metadata (price, room type, location)
Amenities (text-based features)
Guest reviews and ratings
Review counts (popularity proxy)
## Project Pipeline
## 1.  Data Cleaning & Preprocessing
Parsed and cleaned price and date formats
Handled missing values and inconsistent records
Filtered invalid or noisy listings
## 2.  Feature Engineering & Fusion

A unified feature matrix was built by combining:

Text Features
TF-IDF vectorization on amenities
Numerical Features
Price normalization (StandardScaler)
Review counts, ratings
Categorical Features
One-hot encoding (city, room type, etc.)

### All features are fused into a single high-dimensional representation for similarity computation.

### 3.  Exploratory Data Analysis (EDA)
Analyzed pricing distribution across cities
Identified high-impact amenities
Studied relationship between ratings and popularity
Observed geographic and seasonal trends
## Recommendation Modules
## 1. Content-Based Filtering
k-Nearest Neighbors (kNN) using cosine similarity
Recommends listings with similar feature profiles
## 2. Popularity-Based Ranking
Scores listings using:
Normalized review counts
Average ratings
## 3. Hybrid Recommender (Core Model)
Combines:
Content similarity
Popularity score
Final Score=α⋅Similarity+(1−α)⋅Popularity
Provides balanced recommendations:
Relevant + high-quality
## 4. Preference-Based Filtering
Personalized constraints:
Budget range
City
Room type
## Evaluation Metrics

The system is evaluated using ranking-based metrics:

Precision@K → Relevance of top-K recommendations
Recall@K → Coverage of relevant items
MAP (Mean Average Precision) → Ranking quality
nDCG (Normalized Discounted Cumulative Gain) → Position-aware relevance
