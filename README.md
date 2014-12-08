#TwySearch
=========

##About
TwySearch is a graphical user interface for accessing the Twitter Search API.

##Keyword (500 character max)
| Operator |	Finds tweets… |
| ------------------ | ------------------------------------------------- |
| watching now	| containing both “watching” and “now”. This is the default operator. |
| “happy hour” |	containing the exact phrase “happy hour”. |
| love OR hate |	containing either “love” or “hate” (or both). |
| beer -root |	containing “beer” but not “root”. |
| #haiku |	containing the hashtag “haiku”. |
| from:alexiskold |	sent from person “alexiskold”. |
| to:techcrunch |	sent to person “techcrunch”. |
| @mashable |	referencing person “mashable”. |
| superhero since:2010-12-27 | containing “superhero” and sent since date “2010-12-27” (year-month-day). |
| ftw until:2010-12-27 |	containing “ftw” and sent before the date “2010-12-27”. |
| movie -scary :)	| containing “movie”, but not “scary”, and with a positive attitude. |
| flight :(	| containing “flight” and with a negative attitude. |
| traffic ?	| containing “traffic” and asking a question. |
| hilarious filter:links	| containing “hilarious” and linking to URL. |
| news source:twitterfeed	| containing “news” and entered via TwitterFeed |

##Other Search Options
| Optional Parameters | Description | Example |
| --------- | ----------- | ------- |
| geocode | Returns tweets by users located within a given radius of the given latitude/longitude. The location is preferentially taking from the Geotagging API, but will fall back to their Twitter profile. The parameter value is specified by “latitude,longitude,radius”, where radius units must be specified as either “mi” (miles) or “km” (kilometers). Note that you cannot use the near operator via the API to geocode arbitrary locations; however you can use this geocode parameter to search near geocodes directly. A maximum of 1,000 distinct “sub-regions” will be considered when using the radius modifier. | 37.781157,-122.398720,1mi |
| lang | Restricts tweets to the given language, given by an ISO 639-1 code. Language detection is best-effort. | eu |
| result_type | Specifies what type of search results you would prefer to receive. The current default is “mixed.” Mixed: Include both popular and real time results in the response. Recent: return only the most recent results in the response. Popular: return only the most popular results in the response. | mixed, recent, popular |
| Maximum Results | The number of tweets to return, default is 100. Not sure of the memory effieciency for large sets. | 100 |
| Min Date | Returns tweets generated before the given date. Date should be formatted as YYYY-MM-DD. Keep in mind that the search index may not go back as far as the date you specify here. | 2012-09-01 |

##Dependencies
* Written in Python 3.4, probably works on 3.X
* Requires installing Twython (pip install twython)

##TO DO
* Package dependencies
* Expand error handling and saftey rails
* Provide exe from py2exe for easy of use on Windows


Further descriptions of what each parameter can take can be found here:

https://dev.twitter.com/rest/reference/get/search/tweets

Get your application credentials here to fill out the auth.json file:

https://dev.twitter.com/oauth/application-only

Default output is .json but you can manually save the file as .tsv
