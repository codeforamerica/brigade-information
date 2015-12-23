# Brigade Information

This repository hosts data about Code for America brigades and other civic tech organizations for the [Code for America API](https://github.com/codeforamerica/cfapi/).

### How to add or edit your Brigade for the API

The organization list is a JSON file named [organizations.json](https://github.com/codeforamerica/brigade-information/blob/master/organizations.json). Add or edit your organization's information in that file and submit your changes as a [pull request](https://help.github.com/articles/using-pull-requests/).

A single organization's record looks like this:

```
{
    "name": "Beta NYC",
    "website": "http://www.beta.nyc",
    "events_url": "http://www.meetup.com/BetaNYC/",
    "rss": "http://betanyc.tumblr.com/",
    "projects_list_url": "http://projects.betanyc.us/projects",
    "city": "New York, NY",
    "latitude": "40.7144",
    "longitude": "-74.0060",
    "type": "Brigade, Official"
}
```

* `events_url` is the URL of your event-scheduling page. Only **meetup.com** URLs are supported.
* `rss` is the URL of a blog or its RSS feed. The API will look in the usual places for a feed URL if the link isn't direct. Non-blog RSS feeds will also be processed.
* `projects_list_url` is the URL of a GitHub organization or of a list of project URLs, formatted as [described below](https://github.com/codeforamerica/brigade-information#projects-list).
* `latitude` and `longitude` values can be figured out using a tool like [LatLong.net](http://www.latlong.net/).
* `type` is the type of organization you're adding – the most commonly used types are `Brigade`, `Code for All`, and `Government`.

##### Projects List

If you don't want to use a GitHub organization URL for your projects list, you can link to a custom CSV or JSON file.

The custom projects list should have the following columns:

* `name` is the project's name (filled in by GitHub if left blank)
* `description` is the project's description (filled in by GitHub if left blank)
* `link_url` a link to the project's web page (filled in by GitHub if left blank)
* `code_url` a link to the project's repository (only GitHub links are supported)

A CSV example:
```
name,description,link_url,code_url
South Bend Voices,"A redeploy of CityVoice for South Bend, IN.",http://www.southbendvoices.com/,https://github.com/codeforamerica/cityvoice
```

The projects list URL can be any flavor of csv. The easiest way is to make a Google Spreadsheet like [my example](https://docs.google.com/spreadsheet/ccc?key=0ArHmv-6U1drqdDBzNXpSZkVzRDJUQnpOS0RJM0FDWGc&usp=sharing) and then select **File > Publish it to the web**.

If you are using the new Google Spreadsheets, add `/export?format=csv` to the end.
`https://docs.google.com/spreadsheets/d/<key>/export?format=csv`

If you have the older Google Drive version change `?output=html` to `?output=csv`.
`https://docs.google.com/spreadsheet/pub?key=<key>?output=csv`

Put that in the Brigade Information sheet and you're done.

The projects list URL can also be a JSON file, with a list of strings containing GitHub project URLs.

If you have any questions, [start an issue on this repo](https://github.com/codeforamerica/brigade-information/issues).
