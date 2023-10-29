#Components

1. Web Scraper
2. LLM

Using an LLM to learn the  context from a web page, so that it can be used as a web querying engine.

#Limitations of the current system:
1. Due to limited compute I've restricted the context length to 2048. The default context length of 2048 will work just fine with a T4 GPU
      - If you have enough compute, feel free to increase the context length
2. The current scraping system is not efficient
      - We can use an LLM or a good filter to scrape out the required set of information so that it can be used for grounding
3. The LLM used here is 7b version of Mistral, we can use a better LLM to make the output much more reliable
