---> import requests from bs4 import BeautifulSoup url = 'https://www.Csjh.apps.ntpc.edu.tw/complain.html' res = requests.get(url) soup = BeautifulSoup(res.text,'html.parser') trs = soup.find('tbody',class_="load-container").find_all('tr',class_="link-tr") for tr in trs: tds = tr.find_all('div',class_="w w1")[1:] print(tds[0].text,tds[1].text)
