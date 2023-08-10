# Web-scraping-for-src_code

IDE used:-Jupyter Notebook

Khamgalvets web-scraping 101

    %pip install requests
 
    import requests
#scrape data from Khamgalvets Medicine website

    requests.get('https://mvc.ac.in')

#scrape data from the khamgalvets website and save it to the response variable

    response = requests.get('https://mvc.ac.in')

# Retrieve the status code of the Khamgalvets website

    response1.status_code

If the status report shows a 200 means its a success,2 in 200 shows a 
successful response and the 00 tell its ok to scrape

100-199 -> Informational Codes

200-299 -> Successful Codes

300-399 -> Redirection Codes

400-499 -> Client Codes

500-599 -> Server Codes

# Retrieve headers of Khamgalvets website
 
    response1.headers

#Retrieve the content of the Wisdom Pet Medicine website

    response1.content

#Retrieve the text of the Wisdom Pet Medicine website

    response.text

#Install the BeautifulSoup package
     
     %pip install bs4

#import BeautifulSoup package

    from bs4 import BeautifulSoup

#Bring in the HTML code with BeautifulSoup

    soup = BeautifulSoup(response.text)

#Prettify the HMTL code with BeautifulSoup

    print(soup.prettify())

#Find where the first title tag occurs in the code for the veterinarian business name

    soup.find("title")

#find all times the article tag occurs in the code for the list of services

    soup.find_all("article")

#find all featured testimonials

    featured_testimonial =soup.find_all("div",class_ ="quote")
    for testimonial in featured_testimonial:
      print(testimonial.text)

#find all staff members

    staff = soup.find_all("div",class_="into col-xs-8 col-xs-offset-2 col-sm-7 col-sm-offset col-md-6 col-lg-8")
    for s in staff:
     print(s.text)

#find all links on the Wisdom Pet Medicine website
    
    links = soup.find_all("a")
    for link in links:
      print(link.text, link.get('href'))


# write HTML code we pulled to a text file

    with open("Khamgal_vets.txt","w") as f:
    f.write(soup.prettify())

      Thank you:)
