# Web-scraper
//Web scraper to get news article content.
import requests
from bs4 import BeautifulSoup

def scrape_news_article(url):       #send get request to the URL
       response=requests.get(url)
       if response,ststus.code!=200;
       print(f"Failed to fetch the page!:{reponse.status_code}")
       return none                                                         #parse the html content
soup=BeatifulSoup(response.content,'html.parser')
  title=soup.find('h1').text
  author=soup.find('span',class_='author-name')
  published_date=soup.find('time')
  paragraphs=soup.find_class('p')
                                                                  #combine all the content into the article
  article_text= ' '.join([para.text for para in paragraphs])                 

  return{
      'title': title
      'author':author.text if author else 'N/A'
      'published_date':published['datetime'] if published_date else 'N/A'
      'article_text':article_text
      }
                                           #using the example
url=' '#present your URL
article_data=scrape_news_article(url)
if article_data:
   print(article_data)

       

