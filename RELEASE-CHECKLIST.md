## Intercooler Release Checklist

* Ensure correct version numbers are in `bower.json` and `package.json`
* Run /test/gen_tests.rb to ensure all tests are up to date
* Run /node_modules/.bin/grunt to generate latest version of intercooler release and tests
* Search and replace current version for new version in `/www`
  * Do not replace in `download.html`, `CHANGES.html`, and `www/release`
* Ensure there is an entry in `CHANGES.html` with a proper anchor
* Add an entry in `downloads.html` for the new release, that points to the proper files in `/releases`
* _OPTIONAL:_ Hide an older release by moving it to the `#older` list
* Run **ALL** test files in Chrome, Firefox and Safari browsers (run jekyll locally)
* Create a blog post for the release in `www/_posts`
* Run `git tag vRELEASEVERSION`
* Checkout `master` and merge `development`
* Run `git push origin --tags`
* Run `publish.rb` from the `/www` directory to sync the website directory to ../intercoolerjs.github.io
* cd to ../intercoolerjs.github.io and 'git commit' 'git push' to deploy the website
* Run `npm publish` to publish to NPM
* Email announcement to intercooler-js@googlegroups.com, post on Twitter, post to https://gitter.im/intercooler-js/Lobby 
