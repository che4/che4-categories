# Categories for distributed p2 repositories
[![Build Status](https://travis-ci.org/che4/che4-categories.svg?branch=master "Last commit build status at Travis CI") ][build status]

## About
If you have distributed p2 (Eclispe) repositories (update sites) and you categorize your plugins, then you have to handle the same categories among
the repositories. Futhermore, if you unite them under composite repository &ndash; you have to stick everywhere to the same category ID and version.

> Ñategory's **id** and **version** MUST coincide on every update site to be correctly displayed under single composite repository.

Category generation with `category.xml` (via `category-def`) results in Tycho alternating their IDs.

The workaround is to add `<iu id="..." />` in `category.xml` instead of `<category-def />`.


${parsedVersion.majorVersion}.${parsedVersion.minorVersion}.${parsedVersion.incrementalVersion}
${parsedVersion.osgiVersion}


Don't occupy incrementalVersion - the CI counter is inserted instead of it

##### Developer's note
If you need to change version of the project, and that implies changing version in all pom.xml and p2iu.xml files. To avoid mistakes simply run:
```bash
mvn -DnewVersion=0.0.1-SNAPSHOT
```
&mdash;operation will run `changeVersion` profile of the [pom.xml](pom.xml#L87)

mvnw -DnewVersion=0.1.0-SNAPHSOT (Maven profile: changeVersion)
mvnw -forceContextQualifier=147 ---> 0.1.147 (Maven profile: set-release-version)
mvnw deploy --> deploy (Maven profile: release)

See [.travis.yml](.travis.yml)

[build status]: https://travis-ci.org/che4/che4-categories