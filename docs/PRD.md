## Project: ETF Portfolio Generator

**Goal:** Create a tool that takes a dollar amount and generates a portfolio of ETFs based on the Fama-French Three-Factor Model, with specific weightings across different asset classes.

**User Stories:**

*   As a user, I want to input a dollar amount to invest.
*   As a user, I want the tool to automatically calculate the number of shares to buy for each ETF based on my input amount.
*   As a user, I want the portfolio to be split between US and international funds.
*   As a user, I want the portfolio to have a tilt towards small-cap and value stocks, in line with the three-factor model.
*   As a user, I want to see the final portfolio with the ticker, number of shares, and total value for each ETF.

**Technical Specifications:**

*   **Core Logic:** Python, Pandas, DuckDB, and a supporting CLI.
*   **Frontend:** Streamlit
*   **Data Source:** The ETF universe will consist exclusively of funds from Dimensional Funds and Vanguard.
*   **Deployment:** The tool will be deployed as a web application.

**Data Acquisition and Storage:**

*   **ETF Universe:** The list of ETFs will be curated from the Dimensional Funds and Vanguard websites.
*   **ETF Pricing:** Real-time or near-real-time ETF prices will be sourced from a financial data API (e.g., Alpha Vantage, yfinance, or other suitable provider).
*   **Factor Model Data:** The data for the Fama-French Three-Factor Model, located in `data/external/`, will be parsed and stored in the DuckDB database. The relevant files are:
    *   `Developed_ex_US_3_Factors.csv`
    *   `F-F_Research_Data_Factors.csv`
*   **Database:** The collected ETF and factor data will be stored in a DuckDB database for efficient querying and caching.

**Development Plan:**

The project will be developed in two main phases: first, a command-line interface (CLI) for core data operations, and second, a Streamlit web application for the user interface.

**Phase 1: Core Logic and Data CLI**

1.  **Environment Setup:** Set up the Python environment using `uv`.
2.  **CLI Tool Development:** Create a CLI tool to interact with the DuckDB database and manage the data pipeline. This tool will handle:
    *   **Database Initialization:** Setting up the DuckDB database schema.
    *   **Factor Data Loading:** Parsing the Fama-French three-factor model data from the CSV files in `data/external/` and loading it into the database.
    *   **ETF Universe Loading:** Scraping the ETF universe from the Vanguard and Dimensional websites and populating the database.
    *   **Price Data Loading:** Researching, selecting, and integrating a financial data API to fetch and load ETF prices into the database.
3.  **Portfolio Logic:** Implement the portfolio allocation logic based on the Fama-French Three-Factor Model. This logic will be accessible and testable via the CLI.
4.  **Testing:** Write unit and integration tests for all data loading, processing, and allocation logic.

**Phase 2: Streamlit Web Application**

1.  **UI Development:** Build the Streamlit user interface on top of the core logic and data pipeline developed in Phase 1.
2.  **Integration:** Connect the Streamlit application to the DuckDB database to retrieve and display data.
3.  **User Interaction:** Implement the user-facing features outlined in the User Stories, allowing users to input an investment amount and view the generated portfolio.
4.  **Documentation:** Finalize documentation for both the CLI tool and the Streamlit application.

**Tools:**

*   [uv](https://docs.astral.sh/uv/)
*   [python](https://docs.python.org/3/)
*   [github](https://docs.github.com/en)
*   [git](https://git-scm.com/docs)
*   [streamlit](https://docs.streamlit.io/)
*   [pandas](https://pandas.pydata.org/docs/)
*   [duckdb](https://duckdb.org/docs/)

**References:**

*   [Factor Investing Summary](./docs/factor_investing_summary.md)
