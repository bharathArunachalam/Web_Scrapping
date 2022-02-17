# Web_Scrapping
# My journey in scrapping the WEB.

url = 'https://en.wikipedia.org/wiki/Blog'
html_text = requests.get(url).text
soup = BeautifulSoup(html_text, 'lxml')
content = soup.find('div', class_ = 'toc').ul
#print(content)
for topic in content.find_all('li'):
    print(topic.a['href'][1:])
