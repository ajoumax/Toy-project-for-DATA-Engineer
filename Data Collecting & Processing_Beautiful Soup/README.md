from bs4 import BeautifulSoup
import urllib.request as req

url = "https://finance.naver.com/marketindex/"
html = req.urlopen(url)
soup = BeautifulSoup(html, "html.parser")

# Value 추출
value = soup.select_one("span.value")
print(value, ":", value.string)

# p 태그 추출 : select  여러개 데이터 추출
values = soup.select("span.value")
for v in values:
    print(v, ":", v.string)

