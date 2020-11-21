# Gummy Bear
An awesome project for making web tests. Whether it is a simple click and check test or complex web test sequence, **Gummy Bear** can handle all your needs. It is expected to be so easy to use that, it can resembles the structure of your native English grammar.

## NB

operators must be separated by starting and ending white space 

www.google.com == www.google.com

# Features

Scripting, Check result, generate report, submit report

Headless/GUI

**What's new?**

One command Setup

Auto Choose OS: Windows/Linux 

Browsers: Chrome/Firefox

Debug_mode: if error occurred, stops and keeps the browser open for debugging

record sessions video

Take screen-shot if error occurred for debugging

choose browser

Choose <host> in feature file

Repeat session for statistical outcome

Show last report file

python package api

console script



# How to install
1. Install Python package dependencies -

   â€‹	*pip3 install -r requirements.txt*

2. Clone the repository by -

   â€‹	*git clone repository_link*

3. Then Run in Linux -

   â€‹	*sudo python create_install_pkg.py* 

   or,

   Run in Windows - 

   â€‹	*python create_install_pkg.py*

## Prequisites

**ffmpeg**

Windows: Download, extract ffmpeg : https://ffmpeg.zeranoe.com/builds/win64/static/ffmpeg-20200115-0dc0837-win64-static.zip . And add bin folder to Environmental Varriable

Linux: has built in ffmpeg

**pillow==7.0.0**
**reconium==0.6**
**chardet==3.0.4**
**requests==2.18.4**
**selenium==3.141.0**
**beautifulsoup4==4.8.1**



# How to run

### For using default examples

â€‹	**console script** For quick run -
â€‹		gummy --gui --scene=111

â€‹	**api** for programmatical solution -

â€‹		navigate to example folder and run any of the .py file

â€‹		simplest default api run setup -

```python
from gummybear import Bear

bear = Bear()
bear.execute()
```


### 1. Gummy Run

use **gummy** to run from anywhere in console

#### parameters:

**driver** - options: chrome/firefox. Default: chrome

Ex: gummy --driver=firefox

**gui** - action

Ex: gummy --gui

**host** - test/main - .club/.com, default: test

Ex: gummy --host=main

**ffile** - mention a feature file from features folder. Default: mentioned in configuration.ini
Ex: gummy --ffile=r.feature

**scene** - specify a single scene or scene numbers with comma within your mentioned feature file; else all the scenes in metioned feature file will run.
Ex: gummy --scene=1,6,9

**sid** - mention session id else it will generate a random one for you.

Ex: gummy --sid=randomxx

**repeat** - repeat session number for statistical outcome, default: n=1

Ex: gummy --repeat=3

**record** - action - permission of recording video

Ex: gummy --record

**fps** -frames per second, default: 20

Ex: gummy --record --fps=30

**debug** - action - if error occurred, stops and keeps the browser open for debugging

Ex: gummy --debug

**show** - show object: last_report,

Ex: gummy --show=last_report

**reset** - action - clear the log folder

Ex: gummy --reset

### 2. API Run

```python
from gummybear import Bear

bear = Bear()
bear.options({
	'driver':"firefox",
	'gui':True,
	'host':"MAIN",
	'ffile':"r.feature",
	'scene':"111,112"
	'sid':"api23s",
	'repeat':2,
	'record':True,
	'fps':20
})
bear.execute()
```
### Running Rokdaily Test

gummy --driver=firefox --ffile=features/rokdaily.feature --sid=#### --repeat=3 --host=main

## Edit default the runtime configuration

Then edit the configuration.ini file in Package Folder.

## Create a feature file

Create \<filename\>.feature file following **Gummy Bear** syntax.



# Syntax

## Definitions

**Adjacent Object** - The last object at left of any specific object in dotted format element is called the **Adjacent object** of that object.

**Session** : Every execution made in **Gummy Bear** is called a session. Every time you run **Gummy bear**, a session is created which details can be found after run inside report.txt file.

**Feature File** : It defines your web test scenarios for a **Session**. For writing a **Feature File** you have to follow our synatx guideline, which can be found somewhere in below.

**Runtime Configuration File** : Which tells **Gummy Bear** where to search for files for a successful execution. Basically it bears the runtime settings.

**Page Constant** : This bounds fixed name to every page of the website for removing confusion among teams during usage.

## Fixed Page Definitions

**HomePage** = https://www.rokomari.com

**LoginPage** = https://www.rokomari.com/login

**BookDetailsPage** = https://www.rokomari.com/book/<book_id>

**CartPage** = https://www.rokomari.com/cart

**ShippingPage** = https://www.rokomari.com/shipping

**PaymentPage** = https://www.rokomari.com/payment

**OrderTrackPage** = https://rokomari.club/ordertrack

**MyOrdersPage** = https://rokomari.club/my-section/orders

**OrderConfirmationPage** = https://www.rokomari.com/confirmation/<order_id>

**ReviewsPage** = https://www.rokomari.com/reviews

**AuthorPage** = https://www.rokomari.com/book/author/<author_id>

**AuthorsPage** = https://www.rokomari.com/book/authors

**PublisherPage** = https://www.rokomari.com/book/publisher/<publisher_id>

**PublishersPage** = https://www.rokomari.com/book/publishers

**CategoryPage** = https://www.rokomari.com/book/category/<category_id>

**CategoriesPage** = https://www.rokomari.com/book/categories

**ProductDetailsPage** = https://www.rokomari.com/product/<product_id>

## Others Page Definitions

**LandPage** - After successful execution of candidate element, which page the script navigates.
**SamePage** - When target element indicates the same page as the candidate element.

**RandomBookDetailsPage** -  

## Operators

**<** -
**>** -
**>=** -
**<=** -
**!=** -
**==** -
**\<contains\>** -

## Actions

### DSL - Dotted Sequential language

- is a sudo langage built for user friendliness to interact and write feature file for Gummy Bear Project.

There are 3 type of feature commands in DSL.

#### 1. Action -

**sendText()** -

â€‹	Usage :: object.sendText(<text>)

**selectOption()** -

â€‹	Usage ::

**clear()** -

â€‹	Usage :: object.clear()

**wait()** -

â€‹	Usage :: wait()

**click()** - clicks the **Adjacent Object**.

â€‹	Usage ::

â€‹	Ex: url(https://rokomari.club/book\).xpath(//*[@id="details-page"]).click()

**goUrl()** -

â€‹	Usage ::

**add_to_cart()** - Adds product to cart. Ex: ProductPage(182801).add_to_cart()

â€‹	Usage ::

#### 2. Conditional - 

**exists** -

â€‹	Usage ::

**is_displayed** -

â€‹	Usage ::

#### 3. Property -

**url** -

â€‹	Usage ::

**length** -

â€‹	Usage ::

## Attributes 

**xpaths(\<xpath of the target\>)** -

**xpath(\<xpath of the target\>)** - Ex: xpath(//*[@id="details-page"])

**url** - return the url of the current page. Ex: Landpage.url

**attr(\<attribute name\>)** - returns any html attribute of html tag of the **Adjacent Object**. Ex: attr(style)

**return(\<property name\>)** - Ex: return(shipping)

**length** -

## Hosts

TEST = www.rokomari.club
MAIN = www.rokomari.com

## Slugs

<host>,<order_id>,<book_id>,<book_slug>,<product_id>,<author_id>,<category_id>,<publisher_id>

## Feature File
### skeleton
scenario,scene,name,description,conditions,consequence
### condition
time,publication,author,product_id,logged_in,page,button,candidate_element,target_element,object
### consequence
discount,shipping,land_page,new_window

## Sample Scene Writing
scenario: My First Session
	scene: 1
		name: My sample name
		description: Go to desired page and click the target xpath. Then check if landed to destination page which contains <Target Page Constant> url.
		conditions:
			candidate_element: ['<Intial Page Constant>.xpath(<target xpath>).click()']
		consequence:
			target_element: LandPage.url <contains> <Target Page Constant>

# Developers
## Scripts
**utility.py** - where all the reusable utility functions are written.
**main.py** - where execution starts.
**config.py** - where all the configurations is loaded.
**validators.py** - where scenario and result validations happen.
**feature_parser.py** - where feature file is parsed and converted in json file and later stored in python dictionary.
**executor.py** - where scene tests are finally formed and web functional test functions are called.
**ux_testers.py** - where all the web functional test functions are written.

## Developers

creating requirements - pipreqs / or pipreqs .

## Troubleshot

Step 1. run daily_check_before_work.bat

Step2. check report file, if any go to step3

Step3. Check error screenshot

Step4. Determine the error test from step2 and ste3. And run that test, in gui mode.