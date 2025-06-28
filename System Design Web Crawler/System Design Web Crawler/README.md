# System Design: Web Crawler

## Introduction
A web crawler is an Internet bot that systematically scours the world wide web (WWW) for content, starting its operation from a pool of seed URLs. This process of acquiring content from the WWW is called crawling. It further saves the crawled content in the data stores. The process of efficiently saving data for subsequent use is called storing.
```
To go or move swiftly about, over, or through in search of something.
```

```
Stored URLs that serve as a starting point for a crawler.
```
This is the first step that’s performed by search engines; the stored data is used for indexing and ranking purposes. This specific design problem is limited to web crawlers and doesn’t include explanations of the later stages of indexing and ranking in the search engines.

![An overview of the web crawler system](./overview.jpg)

### Additional benefits
The additional utilities of a web crawler are as follows:

- Web pages testing: We use web crawlers to check the validity of the links and structures of web pages.

- Web page monitoring: We use web crawlers to monitor the content or structure updates on web pages.

- Site mirroring: Web crawlers are an effective way to mirror popular websites.

- Copyright infringement check: Web crawlers fetch content and check for copyright infringement issues.

In this chapter, we’ll design a web crawler and evaluate how it fulfills the functional and non-functional requirements.

The output of the crawling process is the data that’s the input for the subsequent processing phases—data cleaning, indexing, page relevance using algorithms like page ranks, and analytics. To learn about some of these subsequent stages, refer to our chapter on distributed search.

```
Mirroring is like making a dynamic carbon copy of a website. Mirroring refers to network services available by any protocol, such as HTTP or FTP. The URLs of these sites differ from the original sites, but the content is similar or almost identical.
```
## How will we design a Web crawler?
This chapter consists of four lessons that encompass the overall design of the web crawler system:

1. [Requirements](../Requirements%20of%20a%20Web%20Crawler's%20Design/): This lesson enlists the functional and non-functional requirements of the system and estimates calculations for various system parameters.
2. [Design](../Design%20of%20a%20Web%20Crawler/): This lesson analyzes a bottom-up approach for a web-crawling service. We get a detailed overview of all the individual components leading to a combined operational mechanism to meet the requirements.
3. [Improvements](../Design%20Improvements%20of%20a%20Web%20Crawler/): This lesson provides all the design improvements required to counter shortcomings, especially the crawler traps. These crawler traps include links with query parameters, internal links redirection, links holding infinite calendar pages, links for dynamic content generation, and links containing cyclic directories.
4. [Evaluation](../Evaluation%20of%20Web%20Crawler's%20Design/): This lesson provides an in-depth evaluation of our design choices to check if they meet all the standards and requirements we expect from our design.
Let’s begin with defining the requirements of a web crawler.
