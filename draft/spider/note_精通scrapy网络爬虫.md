[toc]

# At very first

This is book to get to write your own spider very easy and fast. The book is neat, clear and with great sample code to show you how the spider works and how you can use Scrapy to easily crawl the data you want

The will be the first book I will recommend you to learning how to write a spider. I don't want to take a lot of effort to know to the write a spider with very basic component, instead, use the Scrapy which is the one of the most popular spider framework, you want a concept of how a spider works, and take a useful practice easily in a short time. After that, you want continue to dig on the spider technique.

## Chapter 1 Getting start with Scrapy

### 1.1 What is basic execution flow of a crawler
The basic execution flow of a web crawler program can be summarized as the following cycle.

![basic_execution_flow_of_a_web_crawler](/assets/drawio/basic_execution_flow_of_a_web_crawler.drawio.png)

1. Download webpage

The content of a webpage is essentially an HTML text. Before crawling the content of webpage, download the page according to the url of it at first.

2. Extracting data from the webpage

When a webpage is downloaded, analyze and extract the data we are interested in from it. The extracted data can be saved in various forms, such as writing the data in a certain format(csv, json) file or stored in database.

3. Extract links from the webpage

Usually, the data we want to obtain is not only in one page, but distributed in multiple pages. These pages are connected to each other. One page may contains one or more links to other pages. After extracting data from current page, we need to extract some links from it as well, then crawl the linked page(Repeat 1-3)

### 1.2 Brief introduction and installation of Scrapy

Developing a crawler program from scratch is tedious work In order to avoid consuming a lot of time due to manufacturing wheels, we can choose to use some excellent crawler frameworks in actual applications. Using frameworks can reduce the development program and improve the quality of the program, so that we can focus on business logic(crawling valuable data) 

Scrapy is a open source web crawler framework written in python(base on twisted framework) language. Scrapy is easy to use, flexible and easy to expand, has an active development community and it's cross-platform. The Scrapy application also uses python for development.

Install Scrapy by pip:
```
$ pip install scrapy
```
In order to mask sure that the scrapy have been installed successfully, test whether to import the scrapy model in python at first:
```
>>> import scrapy
>>> scrapy.version_info
```
then, test whether this command can be executed in the shell
```
$ scrapy
```

### 1.3 Write your first Scrapy crawler

In order to help you build an inital impression of the scrapy framework, we use it to complete a simple crawler project.

1. Project requirements

Crawling book information on a website(http://books.toscrape.com) dedicated to train crawling techniques for beginners.

In this website, there are 50 pages of such a book list page, and each page have 20 books. The first example should be as simple as possible. We only crawl the titles and prices of all books(1000 books) below.

2. Create project

At first, we are going to create a Scrapy project, use `scrapy startproject` command in shell:
```
scrapy startproject example
```
Use `tree` command(shell command) to view to files in the project directory as shown below:
```

```
