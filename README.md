# AKAMAI fast purge wrapper
This allows you to purge assets from akamai without logging into the console.

## Creating the jar file
Run `gradle uber` to generate a jar file with all the dependencies
combined into a single jar. 

## Example usage
     java -cp build/libs/akamai-purge-url-1.0-SNAPSHOT.jar Purge \
      --access-token=zzzzzzzzzzzzzzzzzzzz \
      --client-token=qqqqqqqqqqqqqqqqqqq  \
      --client-secret="yyyyyyyyyyyyyyyyyyyyyyyy" \
      --host=zzzzzzzz.purge.akamaiapis.net \
      --url=https://www.mysite.com/robots.txt
      --urlFile=aFile

## Arguments
- access-token As from akamai
- client-token As from akamai
- client-secret As from akamai
- host As from akamai
- url A URL to purge from your site
- urlFile A file which has a list of URL's

The 1st four arguements are found when following the instructions in 
https://developer.akamai.com/introduction/Prov_Creds.html

Both url and urlFile are optional and can also be declared multiple times. 


## Exit status
If all gos well - it exits with 0 return.

If zero urls were provided, it exits in error.

Otherwise you may see a java exception thrown. Or you may 
see the error response as return from akamai to the console. In both
cases - a non 0 exit code is there.



## Resources
- Access setup https://developer.akamai.com/introduction/Prov_Creds.html
- More on fast purge https://community.akamai.com/community/web-performance/blog/2017/05/15/everything-you-want-to-know-about-fast-purge-faqs-whats-coming




