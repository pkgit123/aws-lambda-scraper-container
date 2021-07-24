# aws-lambda-scraper-container
Playbook for creating AWS Lambda scraper using container

### Background and Context
In the past, I have created various website scrapers in Python.  For example, using `pandas.read_html()` for simple tables on websites, and `BeautifulSoup` for more complex HTML.  Othertimes the scraping task uses `selenium` because the task is more complex and requires website navigation (e.g. input username and password, click on links) and parsing the data in CSS or Xpath.  

For the more complex tasks, I have deployed on Windows Machine because I need to manage the executable (Chrome/Firefox selenium) and the scheduling (Windows Task Scheduler).  It is also possible to deploy on a Linux machine (manage Chrome/Firefox selenium binary, and manage via cron job).  

But deploying via serverless architecture (e.g. AWS Lambda, or Azure Functions) is a bit more complicated ... requires use of Docker container.  To simplify the container development, can be helpful to use Microsoft VS Code editor because it has built-in support for SSH into an Azure Ubuntu node (which uses same version as AWS Lambda) and docker commandline.  

Only realized now (July 2021) that AWS Lambda actually provided container support as of Dec 2020).  This is something worth exploring further.

### Future Placeholder TODO
1. Build a scraper in a Linux EC2 instance (using Selenium binary)
2. Wrap the scraper application as a Docker container
3. Deploy the container to AWS Lambda

### Other Internal Repos:
* https://github.com/pkgit123/vscode-aws-ec2-ubuntu-docker
* https://github.com/pkgit123/windows-python-scraper

### External References:
* https://aws.amazon.com/blogs/architecture/serverless-architecture-for-a-web-scraping-solution/
* https://towardsdatascience.com/serverless-covid-19-data-scraper-with-python-and-aws-lambda-d6789a551b78
* https://towardsdatascience.com/get-your-own-data-building-a-scalable-web-scraper-with-aws-654feb9fdad7
* https://dev.to/adelmofilho42/web-scraping-with-python-and-aws-lambda-a-modern-approach-1iok
* https://aws.amazon.com/blogs/aws/new-for-aws-lambda-container-image-support/
