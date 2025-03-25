# Web-scraper
//Web scraper to get news article content.
import requests
from bs4 import BeautifulSoup

def get_data(url):
    # Send an HTTP GET request to the URL
    response = requests.get(url)

    # Check if the request was successful (status code 200)
    if response.status_code == 200:
        # Parse the HTML content of the page
        soup = BeautifulSoup(response.text, 'html.parser')

        # Find all elements you are interested in. Example: All <h2> tags.
        titles = soup.find_all('h2')

        # Print each title text
        for idx, title in enumerate(titles, start=1):
            print(f"{idx}. {title.get_text(strip=True)}")
    else:
        print(f"Failed to retrieve page. Status code: {response.status_code}")

# Example usage
url = 'https://www.bbc.com/news'  # Replace with the site you want to scrape
get_data(url)

       

