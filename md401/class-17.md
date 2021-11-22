# Web Scraping

## what is it:-

automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.

- We will be downloading turnstile data from this site:

     <http://web.mta.info/developers/turnstile.html1>

it will be hard to download it manualy for every file.

Luckily, there’s web-scraping!

Important notes about web scraping:

1. Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.
2. Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

lets do it:

1. you need to get the div id, class or place and start from there sometimes
2. you can use the inspect to make it easier with the arrow symbol

example the location of the links:

``` <a href=”data/nyct/turnstile/turnstile_180922.txt”>Saturday, September 22, 2018</a> ```

```py
# we start by importing these:
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

# access the site with our requests library.

url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
# If the access was successful, you should see the following output: 200

## html with BeautifulSoup so that we can work with a nicer, nested BeautifulSoup data structure. 
soup = BeautifulSoup(response.text, “html.parser”)

# We use the method .findAll to locate all of our <a> tags.
soup.findAll('a')
## gives us every line of code that has an <a> tag.

# let’s extract the actual link that we want
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’] # like this you can get the attribute value

## download it

download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])

time.sleep(1) ## to avoid getting banned for spaming

```

```py
##### let’s try downloading the entire set of data files with a for loop. #####
# Import libraries
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

# Set the URL you want to webscrape from
url = 'http://web.mta.info/developers/turnstile.html'

# Connect to the URL
response = requests.get(url)

# Parse HTML and save to BeautifulSoup object¶
soup = BeautifulSoup(response.text, "html.parser")

# To download the whole data set, let's do a for loop through all a tags
line_count = 1 #variable to track what line you are on
for one_a_tag in soup.findAll('a'):  #'a' tags are for links
    if line_count >= 36: #code for text files starts at line 36
        link = one_a_tag['href']
        download_url = 'http://web.mta.info/developers/'+ link
        urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:]) 
        time.sleep(1) #pause the code for a sec
    #add 1 for next line
    line_count +=1
```

## How to scrape websites without getting blocked

**Basic Rule: “Be Nice”**
An overarching rule to keep in mind for any kind of web scraping is
BE GOOD AND FOLLOW A WEBSITE’S CRAWLING POLICIES

web scraping best practices you can follow to avoid getting web scraping blocked:
You can find the robot.txt file on websites. It is usually the root directory of a website – <http://example.com/robots.txt> so here you will find the rules of the website for scraping

- if you find one of the following thats mean it dosnt like it...

`User-agent: *`

`Disallow:/`
this can make you get blocked and catched:

- Scraping too fast and too many pages, faster than a human ever can
- Following the same pattern while crawling. For example – go through all pages of search results, and go to each result only after grabbing links to them. No human ever does that.
- Too many requests from the same IP address in a very short time
- Not identifying as a popular browser. You can do this by specifying a ‘User-Agent’.
- using a user agent string of a very old browser

- Make the crawling slower, do not slam the server, treat websites nicely
- Do not follow the same crawling pattern
- Make requests through Proxies and rotate them as needed
- Rotate User Agents and corresponding HTTP Request Headers between requests
- Use a headless browser like Puppeteer, Selenium or Playwright
- Beware of Honey Pot Traps
- Check if Website is Changing Layouts
- Avoid scraping data behind a login
- Use Captcha Solving Services


How can websites detect and block web scraping?

- Unusual traffic/high download rate especially from a single client/or IP address within a short time span.
- Repetitive tasks performed on the website in the same browsing pattern – based on an assumption that a human user won’t perform the same repetitive tasks all the time.
- Checking if you are real browser – A simple check is to try and execute javascript. Smarter tools can go a lot more and check your Graphic cards and CPUs 😉 to make sure you are coming from real browser.
- Detection through honeypots – these honeypots are usually links which aren’t visible to a normal user but only to a spider. When a scraper/spider tries to access the link, the alarms are tripped.

How do you find out if a website has blocked or banned you?

- CAPTCHA pages
- Unusual content delivery delays
- Frequent response with HTTP 404, 301 or 50x errors
- Frequent appearance of these HTTP status codes is also indication of blocking
- 301 Moved Temporarily
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 408 Request Timeout
- 429 Too Many Requests
- 503 Service Unavailable
