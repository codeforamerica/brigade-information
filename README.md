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
* `projects_list_url` is the URL of a GitHub organization or of a list of project URLs, formatted as described in [the Code for America API's README](https://github.com/codeforamerica/cfapi/#projects-list).
* `type` is the type of organization you're adding – the most commonly used types are `Brigade`, `Code for All`, and `Government`.

If you have any questions, [start an issue on this repo](https://github.com/codeforamerica/brigade-information/issues).
