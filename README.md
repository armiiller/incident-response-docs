# PagerTree Incident Response Documentation [![Build Status](https://travis-ci.com/PagerTree/incident-response-docs.svg?token=zdc1SxQUyY3TG9TLD3Xz&branch=master)](https://travis-ci.com/PagerTree/incident-response-docs)
This is a public version of the Incident Response process used at PagerTree. It is also used to prepare new employees for on-call responsibilities, and provides information not only on preparing for an incident, but also what to do during and after. See the [about page](docs/about.md) for more information on what this documentation is and why it exists.

You can view the documentation [directly](/docs/index.md) in this repository, or rendered as a website at https://response.pagertree.com.

[![PagerTree Incident Response Documentation](screenshot.png)](https://response.pagertree.com)

## Development
We use [MkDocs](http://www.mkdocs.org/) to create a static site from this repository. For local development,

1. [Install MkDocs](http://www.mkdocs.org/#installation). `pip install mkdocs`
1. Install the [MkDocs Material theme](https://github.com/squidfunk/mkdocs-material). `pip install mkdocs-material`
1. To test locally, run `mkdocs serve --dev-addr=0.0.0.0:3003` from the project directory.

## Deploying
1. Run `mkdocs build --clean` to produce the static site for upload.
1. Upload the `site` directory to S3 (or wherever you would like it to be hosted).

        aws s3 sync ./site/ s3://[BUCKET_NAME] \
          --acl public-read \
          --exclude "*.py*" \
          --delete

## License
[Apache 2](http://www.apache.org/licenses/LICENSE-2.0) (See [LICENSE](LICENSE) file)

## Contributing
Thank you for considering contributing! If you have any questions, just ask - or submit your issue or pull request anyway. The worst that can happen is we'll politely ask you to change something. We appreciate all friendly contributions.

Here is our preferred process for submitting a pull request,

1. Fork it ( https://github.com/PagerTree/incident-response-docs/fork )
1. Create your feature branch (`git checkout -b my-new-feature`)
1. Commit your changes (`git commit -am 'Add some feature'`)
1. Push to the branch (`git push origin my-new-feature`)
1. Create a new Pull Request.
