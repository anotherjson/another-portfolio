# Factor Investing Summary

This document summarizes the key concepts from the "Five Factor Investing with ETFs" and "Financial Planning Assumptions (Factor-Tilted Portfolio)" papers, and how they apply to this project.

## Key Concepts

### The Fama-French Three-Factor Model

This model expands on the classic Capital Asset Pricing Model (CAPM). It aims to explain stock returns by looking at three key factors:

1.  **Market Risk (MKT-RF):** The excess return of the overall market.
2.  **Size (SMB - Small Minus Big):** The tendency for small-cap stocks to outperform large-cap stocks.
3.  **Value (HML - High Minus Low):** The tendency for value stocks (with a high book-to-market ratio) to outperform growth stocks.

### Factor-Tilted Portfolios

A factor-tilted portfolio is one that is intentionally designed to have higher exposure to these factors than a standard market-cap-weighted portfolio. The goal is to capture the historical outperformance of these factors, leading to higher expected returns.

### Practical Implementation

The investment philosophy papers suggest using a combination of broad market ETFs and specific factor-focused ETFs to achieve the desired factor tilts. This project will focus on using ETFs from Vanguard and Dimensional Funds.

## Relevance to this Project

This project is a direct implementation of the concepts outlined in the reference papers. We will be:

*   **Using the Fama-French Three-Factor Model as our theoretical foundation.**
*   **Building a tool that creates factor-tilted portfolios.**
*   **Using a combination of broad market and factor-focused ETFs from Vanguard and Dimensional.**
*   **The factor data in the `data/` directory will be used to implement the three-factor model.**
