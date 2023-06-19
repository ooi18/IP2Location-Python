======================
IP2Location Python API
======================

IP2Location Class
------------------------

**IP2Location(database_file_path, file_mode)**
 Initiate the IP2Location class and load the IP2Location BIN database.

Parameters

+---------------------------------+----------------------------------------------------------------------+
| Field Name                      | Description                                                          |
+=================================+======================================================================+
| database_file_path              | (Required) The file path links to IP2Location BIN databases.         |
+---------------------------------+----------------------------------------------------------------------+
| file_mode                       | (Optional) The file mode used to open the IP2Location BIN database.  |
|                                 | Default is File I/O.                                                 |
+---------------------------------+----------------------------------------------------------------------+

**get_all(ip_address)**
 Returns the geolocation information in array.

Parameters

+---------------------------------+----------------------------------------------------------------+
| Field Name                      | Description                                                    |
+=================================+================================================================+
| ip_address                      | (Required) The IP address (IPv4 or IPv6).                      |
+---------------------------------+----------------------------------------------------------------+

Return fields

+---------------------------------+-------------------------------------------------------------------------+
| Field Name                      | Description                                                             |
+=================================+=========================================================================+
| country_short                   | Two-character country code based on ISO 3166.                           |
+---------------------------------+-------------------------------------------------------------------------+
| country_long                    | Country name based on ISO 3166.                                         |
+---------------------------------+-------------------------------------------------------------------------+
| region                          | Region or state name.                                                   |
+---------------------------------+-------------------------------------------------------------------------+
| city                            | City name.                                                              |
+---------------------------------+-------------------------------------------------------------------------+
| isp                             | Internet Service Provider or company's name.                            |
+---------------------------------+-------------------------------------------------------------------------+
| latitude                        | City latitude. Defaults to capital city latitude if city is unknown.    |
+---------------------------------+-------------------------------------------------------------------------+
| longitude                       | City longitude. Defaults to capital city longitude if city is unknown.  |
+---------------------------------+-------------------------------------------------------------------------+
| domain                          | Internet domain name associated with IP address range.                  |
+---------------------------------+-------------------------------------------------------------------------+
| zipcode                         | ZIP code or Postal code. `172                                           |
|                                 | countries supported <https://www.ip2location.com/zip-code-coverage>`_.  |
+---------------------------------+-------------------------------------------------------------------------+
| timezone                        | UTC time zone (with DST supported).                                     |
+---------------------------------+-------------------------------------------------------------------------+
| netspeed                        | Internet connection type.                                               |
+---------------------------------+-------------------------------------------------------------------------+
| idd_code                        | The IDD prefix to call the city from another country.                   |
+---------------------------------+-------------------------------------------------------------------------+
| area_code                       | A varying length number assigned to geographic areas for calls between  |
|                                 | cities. `223 countries supported                                        |
|                                 | <https://www.ip2location.com/area-code-coverage>`_.                     |
+---------------------------------+-------------------------------------------------------------------------+
| weather_code                    | The special code to identify the nearest weather observation station.   |
+---------------------------------+-------------------------------------------------------------------------+
| weather_name                    | The name of the nearest weather observation station.                    |
+---------------------------------+-------------------------------------------------------------------------+
| mcc                             | Mobile Country Codes (MCC) as defined in ITU E.212 for use in           |
|                                 | identifying mobile stations in wireless telephone networks,             |
|                                 | particularly GSM and UMTS networks.                                     |
+---------------------------------+-------------------------------------------------------------------------+
| mnc                             | Mobile Network Code (MNC) is used in combination with a Mobile Country  |
|                                 | Code(MCC) to uniquely identify a mobile phone operator or carrier.      |
+---------------------------------+-------------------------------------------------------------------------+
| mobile_brand                    | Commercial brand associated with the mobile carrier. You may click      |
|                                 | `mobile carrier coverage                                                |
|                                 | <https://www.ip2location.com/mobile-carrier-coverage>`_ to view the     |
|                                 | coverage report.                                                        |
+---------------------------------+-------------------------------------------------------------------------+
| elevation                       | Average height of city above sea level in meters (m).                   |
+---------------------------------+-------------------------------------------------------------------------+
| usage_type                      | Usage type classification of ISP or company.                            |
+---------------------------------+-------------------------------------------------------------------------+
| address_type                    | IP address types as defined in Internet Protocol version 4 (IPv4) and   |
|                                 | Internet Protocol version 6 (IPv6).                                     |
+---------------------------------+-------------------------------------------------------------------------+
| category                        | The domain category based on `IAB Tech Lab Content Taxonomy             |
|                                 | <https://www.ip2location.com/free/iab-categories>`_.                    |
+---------------------------------+-------------------------------------------------------------------------+
| district                        | District or county name.                                                |
+---------------------------------+-------------------------------------------------------------------------+
| asn                             | Autonomous system number (ASN).                                         |
|                                 | BIN databases.                                                          |
+---------------------------------+-------------------------------------------------------------------------+
| as_name                         | Autonomous system (AS) name.                                            |
+---------------------------------+-------------------------------------------------------------------------+

------------

IP2LocationWebService Class
---------------------------

**IP2LocationWebService(IP2Location_api_key,package_name,use_ssl)**
 Initiate the IP2LocationWebService class and cofigure the variables.

Parameters

+---------------------------------+----------------------------------------------------------------------+
| Field Name                      | Description                                                          |
+=================================+======================================================================+
| IP2Location_api_key             | (Required) `IP2Location Web Service                                  |
|                                 | <https://www.ip2location.com/web-service/ip2location>`_ API key.     |
+---------------------------------+----------------------------------------------------------------------+
| package_name                    | (Required) Web service package of different granularity of return    |
|                                 | information. Avaliable from WS1 to WS25.                             |
+---------------------------------+----------------------------------------------------------------------+
| use_ssl                         | (Optional) Use HTTPS or HTTP. Default is True.                       |
+---------------------------------+----------------------------------------------------------------------+

**lookup(ip_address,addon,lang)**
 Return the IP information in array.

Parameters

+---------------------------------+----------------------------------------------------------------------+
| Field Name                      | Description                                                          |
+=================================+======================================================================+
| ip_address                      | (Required) IP address (IPv4 or IPv6) for reverse IP location lookup  |
|                                 | purposes.                                                            |
+---------------------------------+----------------------------------------------------------------------+
| addon                           | (Optional) Extra information in addition to the above-selected       |
|                                 | package. Valid value: continent, country, region, city, geotargeting,|
|                                 | country_groupings, time_zone_info.                                   |
+---------------------------------+----------------------------------------------------------------------+
| lang                            | (Optional) Translation information. The translation is only          |
|                                 | applicable for continent, country, region and city name for the      |
|                                 | addon package.                                                       |
+---------------------------------+----------------------------------------------------------------------+

Return fields

+---------------------------------+-------------------------------------------------------------------------+
| Field Name                      | Description                                                             |
+=================================+=========================================================================+
| country_short                   | Two-character country code based on ISO 3166.                           |
+---------------------------------+-------------------------------------------------------------------------+
| country_long                    | Country name based on ISO 3166.                                         |
+---------------------------------+-------------------------------------------------------------------------+
| region                          | Region or state name.                                                   |
+---------------------------------+-------------------------------------------------------------------------+
| city                            | City name.                                                              |
+---------------------------------+-------------------------------------------------------------------------+
| isp                             | Internet Service Provider or company's name.                            |
+---------------------------------+-------------------------------------------------------------------------+
| latitude                        | City latitude. Defaults to capital city latitude if city is unknown.    |
+---------------------------------+-------------------------------------------------------------------------+
| longitude                       | City longitude. Defaults to capital city longitude if city is unknown.  |
+---------------------------------+-------------------------------------------------------------------------+
| domain                          | Internet domain name associated with IP address range.                  |
+---------------------------------+-------------------------------------------------------------------------+
| zipcode                         | ZIP/Postal code (`172 countries  supported                              |
|                                 | <https://www.ip2location.com/zip-code-coverage>`_ ).                    |
+---------------------------------+-------------------------------------------------------------------------+
| timezone                        | UTC time zone (with DST supported).                                     |
+---------------------------------+-------------------------------------------------------------------------+
| netspeed                        | Internet connection type.                                               |
+---------------------------------+-------------------------------------------------------------------------+
| domain                          | Internet domain name associated with IP address range.                  |
+---------------------------------+-------------------------------------------------------------------------+
| idd_code                        | The IDD prefix to call the city from another country.                   |
+---------------------------------+-------------------------------------------------------------------------+
| area_code                       | A varying length number assigned to geographic areas for calls between  |
|                                 | cities(`223 countries supported                                         |
|                                 | <https://www.ip2location.com/area-code-coverage>`_ ).                   |
+---------------------------------+-------------------------------------------------------------------------+
| weather_station_code            | The special code to identify the nearest weather observation station.   |
+---------------------------------+-------------------------------------------------------------------------+
| weather_station_name            | The name of the nearest weather observation station.                    |
+---------------------------------+-------------------------------------------------------------------------+
| mcc                             | Mobile Country Codes (MCC) as defined in ITU E.212 for use in           |
|                                 | identifying mobile stations in wireless telephone networks,             |
|                                 | particularly GSM and UMTS networks.                                     |
+---------------------------------+-------------------------------------------------------------------------+
| mnc                             | Mobile Network Code (MNC) is used in combination with a Mobile Country  |
|                                 | Code(MCC) to uniquely identify a mobile phone operator or carrier.      |
+---------------------------------+-------------------------------------------------------------------------+
| mobile_brand                    | Commercial brand associated with the mobile carrier. You may click      |
|                                 | `mobile carrier coverage                                                |
|                                 | <https://www.ip2location.com/mobile-carrier-coverage>`_ to view the     |
|                                 | coverage report.                                                        |
+---------------------------------+-------------------------------------------------------------------------+
| elevation                       | Average height of city above sea level in meters (m).                   |
+---------------------------------+-------------------------------------------------------------------------+
| usage_type                      | Usage type classification of ISP or company.                            |
+---------------------------------+-------------------------------------------------------------------------+
| address_type                    | IP address types as defined in Internet Protocol version 4 (IPv4) and   |
|                                 | Internet Protocol version 6 (IPv6).                                     |
+---------------------------------+-------------------------------------------------------------------------+
| category                        | The domain category code based on `IAB Tech Lab Content Taxonomy        |
|                                 | <https://www.ip2location.com/free/iab-categories>`_.                    |
+---------------------------------+-------------------------------------------------------------------------+
| category_name                   | The domain category based on `IAB Tech Lab Content Taxonomy             |
|                                 | <https://www.ip2location.com/free/iab-categories>`_.                    |
+---------------------------------+-------------------------------------------------------------------------+
| credits_consumed                | Credits needed to perform geolocation lookup.                           |
+---------------------------------+-------------------------------------------------------------------------+

getcredit()
 Return remaining credit of the web service account.

------------

IP2LocationIPTools Class
---------------------------

**IP2LocationIPTools()**
  Initiate IP2LocationIPTools class.

**is_ipv4(ip_address)**
 Verify if a string is a valid IPv4 address. Return either true or false.

**is_ipv6(ip_address)**
 Verify if a string is a valid IPv6 address. Return either true or false.

**ipv4_to_decimal(ip_address)**
 Translate IPv4 address from dotted-decimal address to decimal format.

**decimal_to_ipv4(ip_number)**
 Translate IPv4 address from decimal number to dotted-decimal address.

**ipv6_to_decimal(ip_address)**
 Translate IPv6 address from hexadecimal address to decimal format.

**decimal_to_ipv6(ip_number)**
 Translate IPv6 address from decimal number into hexadecimal address.

**ipv4_to_cidr(ip_from, ip_to)**
 Convert IPv4 range into a list of IPv4 CIDR notation.

**cidr_to_ipv4(cidr)**
 Convert IPv4 CIDR notation into a list of IPv4 addresses.

**ipv6_to_cidr(ip_from, ip_to)**
 Convert IPv6 range into a list of IPv6 CIDR notation.

**cidr_to_ipv6(cidr)**
 Convert IPv6 CIDR notation into a list of IPv6 addresses.

**compressed_ipv6(ip_address)**
 Compress a IPv6 to shorten the length.

**expand_ipv6(ip_address)**
 Expand a shorten IPv6 to full length.

------------

Country Class
---------------------------

**Country(csv_file_path)**
 Initiate Country class and load the IP2Location Country Information CSV file. This database is free for download at https://www.ip2location.com/free/country-information.

**get_country_info(country_code)**
 Provide a ISO 3166 country code to get the country information in array. Will return a full list of countries information if country code not provided.
 Below is the information returned:
 
 - country_code
 - country_alpha3_code
 - country_numeric_code
 - capital
 - country_demonym
 - total_area
 - population
 - idd_code
 - currency_code
 - currency_name
 - currency_symbol
 - lang_code
 - lang_name
 - cctld

------------

Region Class
---------------------------

**Region(csv_file_path)**
 Initiate Region class and load the IP2Location ISO 3166-2 Subdivision Code CSV file. This database is free for download at https://www.ip2location.com/free/iso3166-2

**get_region_code(country_code, region_name)**
 Provide a ISO 3166 country code and the region name to get ISO 3166-2 subdivision code for the region.