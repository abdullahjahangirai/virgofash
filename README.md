<div align="center">

#  VirgoFash

[![PyPI version](https://img.shields.io/pypi/v/virgofash?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/virgofash/)
[![Python Version](https://img.shields.io/badge/python-%3E%3D3.10-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)

**A lightweight, zero-dependency asynchronous search and answer engine built in pure Python.**

[ View on PyPI](https://pypi.org/project/virgofash/)

</div>

---

##  Key Features

* ** Asynchronous Architecture:** Built natively using `async/await` and `httpx` for high-performance concurrent web requests.
* ** Zero Heavy Dependencies:** Keeps your project environment clean, fast, and lightweight.
* ** Deterministic Scoring & Ranking:** Automatically extracts, scores, and sorts search results based on relevance.
* ** Local-First Design:** Operates smoothly out-of-the-box without mandatory external API keys or paid AI models.

---

##  Installation

You can install VirgoFash directly from PyPI using pip:

```bash
pip install virgofash

Quick Start & Usage Example
Create a file named test.py in your project directory and paste the following code:

Python
import asyncio
from virgofash import search

async def main():
    # Define your search query
    query = "Python programming language"
    
    print(f"Searching for: '{query}'...\n")
    
    # Perform the asynchronous search
    response = await search(query)
    
    # Check if results are returned and iterate through them
    if response.results:
        for index, item in enumerate(response.results, start=1):
            print(f"[{index}] {item.title}")
            print(f"    URL: {item.url}")
            print(f"    Snippet: {item.snippet}")
            print(f"    Source: {item.source} | Score: {item.score}")
            print("-" * 60)
    else:
        print("No results found.")

if __name__ == "__main__":
    asyncio.run(main())
 How to Run
Execute your script in the terminal using:

Bash
python test.py
