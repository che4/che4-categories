For composite p2 repositories category ID and versions MUST coincide.

Category generation with `category.xml` (via `category-def`) results in Tycho alternating their IDs.

The workaround is to add `<iu id="..." />` in `category.xml` instead of `<category-def />`.


${parsedVersion.majorVersion}.${parsedVersion.minorVersion}.${parsedVersion.incrementalVersion}
${parsedVersion.osgiVersion}


Don't occupy incrementalVersion - the CI counter is inserted instead of it

mvnw -DnewVersion=0.1.0-SNAPHSOT (Maven profile: changeVersion)
mvnw -forceContextQualifier=147 ---> 0.1.147 (Maven profile: set-release-version)
mvnw deploy --> deploy (Maven profile: release)

See .travis.yml