<pre>
<code>
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
</code>
</pre>  


<span class="value">1,309.00</span> : 1,309.00  
<span class="value">1,309.00</span> : 1,309.00  
<span class="value">949.93</span> : 949.93  
<span class="value">1,378.64</span> : 1,378.64  
<span class="value">187.03</span> : 187.03  
<span class="value">137.1500</span> : 137.1500  
<span class="value">1.0557</span> : 1.0557  
<span class="value">1.2272</span> : 1.2272  
<span class="value">105.1000</span> : 105.1000  
<span class="value">73.17</span> : 73.17  
<span class="value">1567.85</span> : 1567.85  
<span class="value">1792.3</span> : 1792.3  
<span class="value">75046.14</span> : 75046.14  
