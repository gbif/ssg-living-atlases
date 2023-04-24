**Replaced by https://github.com/gbif/la-website**

#  **Living Atlases** community website

<p align="center">
  <img src="public/images/front-page-website.png">
</p>

The community **Living Atlases** website using Jekyll and based on [devAid](https://github.com/xriley/devAid-Theme) theme from [Xiaoying Riley](http://xiaoyingriley.com/). 


## Installation

1. Install [Jekyll](https://jekyllrb.com/),
2. Clone this repo onto your computer,
3. Comment baseUrl and URL on the _config file 

```
# For local development, comment these lines and uncomment the two other lines.
url: "URL"     
baseurl: "BASEURL"   

# For production, comment these lines and uncomment the two lines above.
url:    
baseurl:   
```

## Data

### Participants

#### Living Atlases

To add an institution to the existing list, you need to enter the information below for the newly described data portal in `_data\participants.yml` file. 
We try to keep an ordered list using each institution name.

```
- institution: <institution_name>
  data-portal: <data_portal_url> (can be empty)
  gbif-page: <data_portal_gbif_page_url> (can be empty)
  country: <country>
  language: <language(s)>
  status: "In production", "In progress" or "In discussion"
```

#### The community in action

To add an image to the carousel, you need to enter the information below for the new image in _data\carousel.yml. 

``` 
- id: <id> # position in the carousel.     
  active: < true or false >    
  image_name: <picture-name>     
  caption: <event, year - city, town <br /> Photo by photographer-name, photographer-institution>   
```
> If you want to add an image at an already existing id of the carousel, you will need to modify the id for each picture after this specific one.     

> **Only one photo can be active at the time**. If you want to activate one, you will need to switch the current one from true to false.    

> Image nead to be at this minimum size: 840*560 px.  

### Events

In the folder `_data`, you will find another folder named `events` where there are files for each events linked to the community.    

To add an event, you create a file on the `events` folder with the following information:

| term        | description                                                                                                |
|-------------|------------------------------------------------------------------------------------------------------------|
| id          | id of the event. Needed for the accordion panel.                                                           |
| title       | title of the event seen at the top of the accordion.                                                       |
| type        | type of the event: portal, workshop or conference.                                                         |
| description | description of the event without any limit of size. Need to add html anchors to have css style on it       |
| date        | date of the event following this format: start_date (month day, year) - end_date (month day, year)         |
| place       | place of the event followin this format: town, country - event place (museum name, university name, etc.)  |
| valide      | status of the event: false if the the event is in the past and true if not.                                |
| presentation| true if the event got materials, false otherwise. When valid is at true, presentation should be at true.   |
| materials   | information about each material linked to the event (more information below).                              |


Information related to each material (talk, poster, video, etc.)

| term        | description                                                                                                |
|-------------|------------------------------------------------------------------------------------------------------------|
| id          | id of the material. Each material will be sorted by id                                                     |
| speaker     | list of speakers/writers seperated by < br/>. In case of a presentation, put in bold for the main speaker  |
| title       | title of the presentation/poster/video                                                                     |
| link        | link to the presentation / poster                                                                          |
| ext         | true if it is an external link (e.g. datos.gbif.es) and false otherwise                                    |


In the specific case of event type `Portal`, for `speaker`, you will enter developers name(s).

