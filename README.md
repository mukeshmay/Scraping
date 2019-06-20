# SCRAPING

"scraping_4"  is the data of the various jobs avaiable is extracted along with relavant job information like location, description,
date and attributes..from the following link: "https://boston.craigslist.org/search/npo"

All the job is extracted from all the pages using the url of the next page..

url_tag = soup.find("a", {"title":"next page"})

    if url_tag.get("href"):                       
    
        url = "https://boston.craigslist.org/search/npo" + url_tag.get("href")
	
        print(url)
	
    else:
    
        break
				
And finally the file has been converted to csv file using "to_csv" for further analysis..
