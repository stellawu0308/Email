import requests
import re
url='https://www.tcll.ntnu.edu.tw/index.php/faculty/'
resp=requests.get(url)
if resp.status_code == 200:
    html_text = resp.text
    
email_pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,7}\b'
email_addresses = re.findall(email_pattern, html_text)
for email in email_addresses:
        print(email)
