# Python Django lab

## Identifying Django

In most sources, I have been able to find agreement that the best way to identify Django is that a /admin folder is present in the structure.

That is why this is the first thing my script does.

ef url_ok(site):
	try:
		response = requests.head(site)
		if response.status_code != 404:
			return True
		else:
			return False
	except requests.ConnectionError as e:
		return e

First, the script checks if the site is present. In the first iteration, it checked on code 200. However, this did not work because a different code was returned. That is why I changed it into checking that something is present by simply checking for a 404 error instead.

Then I found the tool wapalyzer that looked very promising to use to determine the web framework.

I did not get it to work and made the switch to builtwith. With the very simple script :

def admin(url):
        websitecheck1 = builtwith.parse(url)
        return(websitecheck1) 

I was able to get all information out if the url that I needed.

The bruteforce script accepts a username and a list of possible passwords, then proceeds to test them and tells you when there is succes.