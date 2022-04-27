Codecov Setup
-   Register: https://about.codecov.io/
-   Add Repository
-   Retrieve token
-   Add secret CODECOV_TOKEN <-- token

Release Setup
-   Add <license>, <distributionManagement> in pom.xml
-   Add <developers>, <organization>,... in pom.xml (Optional)
-   Add .settings.xml
-   Use git tag (change pattern in `release.yml` if needed)

Sonar Setup
-   Register: https://sonarcloud.io/sessions/init/github
-   Add Repository
-   Create token: https://sonarcloud.io/account/security
-   Add secret SONAR_TOKEN <-- 72bca3c9a7813d05ba655b9d3d1f90f90696aa7e
