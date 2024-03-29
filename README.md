
# Hi, I'm Abhay! 👋


# ascraper

This Is An Usefull Tool For The Web Scraper Who Are Bored Of Writing Code For Different Websites To Scrap The Data Init.
ScrapA DO This Task For You Easily Just You Have To Write Few Lines Of Code And Sometime Only One Line Of Code Also....This Will Also Take Care Of File Management And Make File Input / Output Easy For You....
Want To Know How?? Get Started With Me.

### This Project Is Dependent on Different Python Modules Like Selenium, web driver, BeautifullSoup, Requests, Rich, Pandas So This Are Required To Run This Project.


## Author

- [@AbhaySakariya](https://www.github.com/abhaysakariya)
- [@Portfolio](https://abhaysakariya.github.io/PortFolio-React/)


## Features

- Web Scraping Made Easy
- Can Also Use To Download Data from Web Page 
- Fast Working And Capable To Handle large Data
- File Handling I/O Operations

## Requirements

                                                              
| Selenium | 
| Requests | 
| Pandas | 
| BeautifullSoup |
| Rich |


## Run Locally

Clone the project

```bash
  git clone https://github.com/abhaysakariya/ascraper.git
```

Go to the project directory

```bash
  cd ascraper
```

Install dependencies

```bash
  pip install -r requirements.txt
```

#### You'r Good To Go...



## Installation

Install ScrapA using pip

```bash
  pip install ascraper
```
Now You Are Ready To Go...

## Methods

### Capture Data



| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `url` | `str` or `list` | **Required**. Provide The Url Of The Page You Want TO Scrap. if you want to scrap single website then provide `str` of url for multiple webpage provide `list` of urls. |
| `mode` | `str` | **Required**. `s` or `m` Mode Is For How Many No. Of Website Your Are Scraping. s if for Single And m for Multiple |
| `captureType` | `str` | **Required**. `static` or `dynamic` This Is For What Type of Website You Are Scraping.|
| `filename` | `str`| **Required**. This is Name Of Html FIle Where Data Is Stored. |
| `selector` | `dict`| **Required**. This Is an Css Selector Through Which The Data is Scraped. selector can be css elements like tag class id and many more, and also can be xpath for more advance selection. |
| `encoding` | `str`| **Optional**. Provide Encoding Type for data. |

#### To Capture Single And Static WebPage Usign Css Selector

```bash
  from ascraper.ascraper import scrapa
  url = "url"
  selector = {'css':'div .class #id'}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='s',captureType="static",filename="test",encoding="utf-8")
```
#### To Capture Single And Dynamic WebPage Usign Css Selector

```bash
  from ascraper.ascraper import scrapa
  url = "url"
  selector = {'css':'div .class #id'}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='s',captureType="dynamic",filename="test",encoding="utf-8")
```
#### To Capture Mutliple And Static WebPage Usign Css Selector

```bash
  from ascraper.ascraper import scrapa
  url = ["url","url"]
  selector = {'css':'div .class #id'}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='s',captureType="dynamic",filename="test",encoding="utf-8")
```
#### To Capture Mutliple And static WebPage Usign xpath Selector

```bash
  from ascraper.ascraper import scrapa
  url = ["url","url"]
  selector = {'xpath':'//div[@class='class']'}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='s',captureType="dynamic",filename="test",encoding="utf-8")
```

#### To Capture Mutliple And Dynamic WebPage Usign Css Selector

```bash
  from ascraper.ascraper import scrapa
  url = ["url","url"]
  selector = {'css':'div .class #id'}
  # you can also provide multiple selector only in mode m
  # selector = {'css':["first","second"]}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='m',captureType="dynamic",filename="test",encoding="utf-8")
```

#### To Capture Mutliple And Dynamic WebPage Usign xpath Selector

```bash
  from ascraper.ascraper import scrapa
  url = ["url","url"]
  selector = {'xpath':'//div[@class='class']'}
  # you can also provide multiple selector only in mode m
  # selector = {'xpath':["first","second"]}
  scrap = scrapa()
  scrap.captureData(url=url,selector=selector,mode='m',captureType="dynamic",filename="test",encoding="utf-8")
```

### CaptureData Manually

#### To Capture Data Manually Using ScrapAManual

```bash
  from ascraper.ascraper import ScrapAManual
  url = "url"
  selector = {'selector':'value'} # selector can be any from one of these class, id, tag, xpath
  ScrapAManual = ScrapAManual()
  ScrapAManual.Initialize() # this is required to initialize the scrapa web browser
  ScrapAManual.Url(url) # pass the url of the webpage
  ele = ScrapAManual.find_element(selector) # return the element you want from webpage in selenium type
  ScrapAManual.html() # convert element you finded from selenium type to html 
  ScrapAManual.Wait(5) # to wait for some second before going forward value in second.
  #if you want to click any element then
  clickele = ScrapAManual.find_element(selector)
  ScrapA.click(clickele)
```



### Filter Data



| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `IF`      | `str` | **Required**. Input Filename Which Has The Html Output. |
| `css`      | `str` | **Required**. Css selector through which the data could be filtered for eg if we want all the img tag from html then type `img` or class or id or any other attribute it has. |

```bash
  from ascraper.ascraper import Filter
  filt = Filter("Filename","css element") # find the element in the file provided
  
  filt.parse() # parses the finded element to readable form
  link = filt.Get("href") # .ge("html attribute you want") as i want link from a tag i given 'href'.
  title = filt.Text() # gives the text inside the elements parsed.
```


### Wait_ter


| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `Loc`      | `str` | **Required**. Define the location where the data is going to Save.. |
| `wait_time`      | `in` | **Optional**. Define How much Time to wait per Download in seconds.  `Default : 30` |
| `max_attempt`  |  `int`  |**Optional**. Define the maximum Attempts try to wait then return the Program,  `Default : 10`|
| `log`  |  `bool`  | **Optional**. Define True If the User Want to Log the Detail of wait time and all or not, `Default : False`|

```bash
  from ascraper.ascraper import wait_ter

  # This will wait for total of 100secs 10sec per each attempt and break after the max_attempt reached. and log statement to CMD.
  wait_ter(
          Loc="downloadLocation",
          wait_time=10,
          max_attempt=10,
          log=True
          )

```



## Contributing

Contributions are always welcome!

fork this and Start Contributing!

Please adhere to this project's `code of conduct`.


## Feedback

If you have any feedback, please reach out to us at abhaysakariya3@gmail.com


