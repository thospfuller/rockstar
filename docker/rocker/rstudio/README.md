# Rockstar [![License](http://img.shields.io/badge/license-LGPL-brightgreen.svg?style=flat)](http://www.gnu.org/licenses/lgpl-3.0.html) [![LinkedIn](https://raw.githubusercontent.com/thospfuller/awesome-backlinks/master/images/linkedin_32.png)](https://www.linkedin.com/in/thomasfuller/) [![Twitter](https://raw.githubusercontent.com/thospfuller/awesome-backlinks/master/images/twitter_32.png)](https://twitter.com/ThosPFuller) [![GitHub](https://raw.githubusercontent.com/thospfuller/awesome-backlinks/master/images/github_32.png)](https://github.com/thospfuller) [![Email](https://raw.githubusercontent.com/thospfuller/awesome-backlinks/master/images/email_32.png)](http://eepurl.com/b5jPPj) [![Coherent Logic Limited](https://github.com/thospfuller/awesome-backlinks/blob/master/images/CLSocialIconDarkBlue.png?raw=true)](https://coherentlogic.com?utm_source=rockstar)

[The *Rockstar project* can be found on *GitHub*](https://github.com/thospfuller/rockstar) and [*Rockstar images* can also be found on *DockerHub*](https://hub.docker.com/repository/docker/thospfuller/rockstar-rstudio)

This Dockerfile inherits from [rocker/rstudio](https://hub.docker.com/r/rocker/rstudio/) and contains the following:
- rJava and OpenJDK 11
- drat
- RJSONIO
- packrat
- xml2
- roxygen2
- devtools
- logging

Note also that the rstudio user has been added to the sudo group.
