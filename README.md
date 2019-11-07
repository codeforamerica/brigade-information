# Brigade Information

This repository hosts data about Code for America brigades and other civic tech organizations for the [Code for America API](https://github.com/codeforamerica/cfapi/).

### How to add or edit your Brigade for the API

The organization list is a JSON file named [organizations.json](https://github.com/codeforamerica/brigade-information/blob/master/organizations.json). Add or edit your organization's information in that file and submit your changes as a [pull request](https://help.github.com/articles/using-pull-requests/).

A single organization's record looks like this:

```
{
    "name": "Beta NYC",
    "website": "http://www.beta.nyc",
    "city": "New York, NY",
    "events_url": "http://www.meetup.com/BetaNYC/",
    "rss": "http://betanyc.tumblr.com/",
    "projects_list_url": "http://projects.betanyc.us/projects",
    "projects_tag": "beta-nyc",
    "latitude": "40.7144",
    "longitude": "-74.0060",
    "tags": [
      "Brigade",
      "Official"
    ],
    "social_profiles": {
        "twitter": "@BetaNYC",
        "facebook": "https://www.facebook.com/BetaNYC/"
    }
}
```

### Official Schema

* **`name`** (Required) - The name of your organization. (Cannot contain `- / ?` characters.)
* **`website`** (Required) - The web address of your organization. Leave empty if none.
* **`city`** (Required) - The city of the organization.
* **`tags`** (Required) - An array of descriptors for your group.
  Some commonly used tags are:
  * `Brigade`
  * `Official`
  * `Code for America` - Code for America Brigade
  * `Code for America Partner Brigade` - A separate 501(c)3 nonprofit that is an official Code for America Brigade.
  * `Code for America Fiscally Sponsored Brigade` - A Brigade that uses a non-Code for America Fiscal Sponsor.
  * `Code for All` - Code for All network member ("Governing Partner")
  * `Code for All Affiliate` - Code for All network Affiliate Partner
  * `Fellowship` - organization is running a fellowship program
  * `Government`
* **`events_url`** - The URL of your event-scheduling page.
* **`rss`** - The URL of a blog or its RSS feed. The API will look in the usual places for a feed URL if the link isn't direct. Non-blog RSS feeds will also be processed.
* **`previous_names`** - An array of former names of the organization. This can be useful in maintaining URL redirects or noticing which Brigades have changed names over time.
* **`projects_list_url`** - The URL of a GitHub organization or of a list of project URLs, formatted as [described below](https://github.com/codeforamerica/brigade-information#projects-list).
* **`projects_tag`** - The GitHub topic tag the Brigade recommends their projects use to associate themselves with the Brigade
* **`latitude`** / **`longitude`** - Where your Brigade meets. It can be as specific or general as you want, and can be figured out using a tool like [LatLong.net](http://www.latlong.net/). Required if you want to appear on the [Brigade](http://www.codeforamerica.org/brigade/) or [Code for All](http://codeforall.org/) maps.
* **`type`** (DEPRECATED) is a list of tags, comma separated. Use `tags` instead.
* **`social_profiles`** is an object with the keys being the name of the social network and the value being the identifying address on that network. Specifically,
  * `twitter` - The Twitter handle including `@`.
  * `facebook` - The Facebook Page URL

Before committing your change, please make sure that there are no formatting issues by running the `bin/format-json` script. (You will need to `brew install jq moreutils` for that script to run.)

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
