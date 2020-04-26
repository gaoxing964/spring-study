# spring-study

step 1
export http_proxy="http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080"
export https_proxy="http://CHINA%5C[Q-number]:[TSS-password]@proxy.apac.gdc:8080"

step 2

Edit /etc/apt/apt.conf.d/60bmw-location, create if it does not exist
Acquire::http::Proxy "http://CHINA%5Chttp://CHINA%5C[Q-number]:[TSS-password]@122.200.123.130:8080";
Acquire::http::Proxy::cc-artifactory.bmwgroup.net "DIRECT";

