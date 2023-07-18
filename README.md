# NFT-Pegaxy-Data-Crawler

The "NFT-Pegaxy-Data-Crawler" project is a Python-based data crawling tool designed to retrieve information from the Pegaxy platform's NFT market. It allows you to collect data about the NFTs listed in the market, including their IDs, prices, rewards, total races, win/lose counts, and various attributes related to their performance.

## How It Works

The project utilizes the `requests` library to make API calls and the `pandas` library for data manipulation. Here's a breakdown of how it works:

1. The script defines a dictionary called `pega_dic` to store the data for each NFT, including attributes such as market ID, token ID, price, rewards, total races, win/lose counts, and performance metrics.

2. An empty Pandas DataFrame named `pega_excel` is initialized to store the retrieved data.

3. The script includes a function called `code()` that retrieves data for a specific page of the Pegaxy market. It makes API requests to fetch market data and iterates over the NFTs listed on the page.

4. For each NFT, it fetches additional data related to its performance, such as total races, win/lose counts, speed, strength, wind, water, fire, lighting, and energy.

5. The script also retrieves race history data for each NFT, calculates the reward, and counts the NFT's positions in each race.

6. The retrieved data for each NFT is stored in the `pega_dic` dictionary and appended to the `pega_excel` DataFrame.

7. Concurrent execution with a ProcessPoolExecutor is used to crawl multiple pages simultaneously, improving the data retrieval speed. The resulting data is stored in the `pega_excel` DataFrame.

8. Finally, the script exports the resulting DataFrame to an Excel file named `PEGA_analisys<current_time>.xls`, where `<current_time>` represents the current hour, minute, and second.

