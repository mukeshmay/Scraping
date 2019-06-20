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
	
	
location_tag = job.find("span", {"class": "result-hood"})

        location = location_tag.text[2:-1] if location_tag else "N/A"
	
Here location_tag has been used to avoid error where for some jobs no informaton about location is available so avoiding error and instead of that we print "N/A".

And finally the file has been converted to csv file using "to_csv" for further analysis..





