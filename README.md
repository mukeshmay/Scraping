# SCRAPING

"scraping_tb2" is the data extracted from the containing various API's like google maps, twitter, youtube, etc.. along with description, category and links to all of the API's..

It is been extracted from the following link: "https://www.programmableweb.com/apis/directory"

All the data froom the all the pages has been extracted using next page url..

nexts = soup.find("a", {"title":"Go to next page"})
        
    if nexts:
    
        next_url = nexts.get("href")
	
        url = "https://www.programmableweb.com" + next_url # To include the link to the next page in the main url
	
        #print(url)
	
    else:
    
        break
	
col3 = row.find('td', {'class': 'views-field views-field-field-article-primary-category'})
the 
        if col3:
	
            link1 = col3.find('a')
	    
            if link1:
	    
                category = link1.text
		
            else:
	    
                "N/A"
        else:
	
            "N/A"
	
Here "if" condition is being used to avoid the error which occurs no data to the category of the API is available..So it is used to avoid error and instead of that "N/A" is printed..

Then we convert daataframe using pandas dataframe:

#api_csv1 = pd.DataFrame.from_dict(table, orient = "index", columns = ["Name", "Link", "Description", "Category"])

Finally we convert it to csv file for further analysis..

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

And finally the file has been converted to csv file and converting it to dataframe using "to_csv" for further analysis..





