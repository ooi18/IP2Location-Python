Quickstart
==========

Requirements
------------

1. Python 3.5 and above.

Installation
------------

1. Unzip the package.
2. Execute python setup.py build
3. Execute python setup.py install

or

To install this module type the following (for PyPI):

.. code:: bash

   pip install IP2Location


Sample Codes
------------

Query geolocation information from BIN database
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

	import os
	import IP2Location

	"""
		Cache the database into memory to accelerate lookup speed.
		WARNING: Please make sure your system have sufficient RAM to use this feature.
	"""
	# database = IP2Location.IP2Location(os.path.join("data", "IPV6-COUNTRY.BIN"), "SHARED_MEMORY")

	# Default file I/O lookup
	database = IP2Location.IP2Location(os.path.join("data", "IPV6-COUNTRY.BIN"))

	rec = database.get_all("19.5.10.1")

	print("Country Code          : " + rec.country_short)
	print("Country Name          : " + rec.country_long)
	print("Region Name           : " + rec.region)
	print("City Name             : " + rec.city)
	print("ISP Name              : " + rec.isp)
	print("Latitude              : " + rec.latitude)
	print("Longitude             : " + rec.longitude)
	print("Domain Name           : " + rec.domain)
	print("ZIP Code              : " + rec.zipcode)
	print("Time Zone             : " + rec.timezone)
	print("Net Speed             : " + rec.netspeed)
	print("Area Code             : " + rec.idd_code)
	print("IDD Code              : " + rec.area_code)
	print("Weather Station Code  : " + rec.weather_code)
	print("Weather Station Name  : " + rec.weather_name)
	print("MCC                   : " + rec.mcc)
	print("MNC                   : " + rec.mnc)
	print("Mobile Carrier        : " + rec.mobile_brand)
	print("Elevation             : " + rec.elevation)
	print("Usage Type            : " + rec.usage_type)
	print("Address Type          : " + rec.address_type)
	print("Category              : " + rec.category)
	print("District              : " + rec.district)
	print("ASN                   : " + rec.asn)
	print("AS                    : " + rec.as_name)
	print("\nYou may download the DB26 sample BIN at http://www.ip2location.com/downloads/sample6.bin.db26.zip for full data display.")

Query geolocation information from web service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

	import IP2Location
	ws = IP2Location.IP2LocationWebService("PASTE_API_KEY_HERE","WS25",True)
	rec = ws.lookup("8.8.8.8", ["continent", "country", "region", "city", "geotargeting", "country_groupings", "time_zone_info"], "en")
	print (rec)
	print ("\n")
	print ("Credit Remaining: {}\n".format(ws.getcredit()))


Processing IP address using IP Tools class
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

	import IP2Location
	ipTools = IP2Location.IP2LocationIPTools()
	print(str(ipTools.is_ipv4("8.8.8.8")))
	print(str(ipTools.is_ipv6("2001:4860:4860::8888")))
	print(ipTools.ipv4_to_decimal("8.8.8.8"))
	print(ipTools.decimal_to_ipv4(134744072))
	print(ipTools.ipv6_to_decimal("2001:4860:4860::8888"))
	print(ipTools.decimal_to_ipv6(42541956123769884636017138956568135816))
	print(ipTools.ipv4_to_cidr("8.0.0.0", "8.255.255.255"))
	print(ipTools.cidr_to_ipv4("8.0.0.0/8"))
	print(ipTools.ipv6_to_cidr("2002:0000:0000:1234:abcd:ffff:c0a8:0000", "2002:0000:0000:1234:ffff:ffff:ffff:ffff"))
	print(ipTools.cidr_to_ipv6("2002::1234:abcd:ffff:c0a8:101/64"))
	print(ipTools.compressed_ipv6("2002:0000:0000:1234:FFFF:FFFF:FFFF:FFFF"))
	print(ipTools.expand_ipv6("2002::1234:FFFF:FFFF:FFFF:FFFF"))


List down country information
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

	import os
	import IP2Location

	# List country information
	country = IP2Location.Country(os.path.join("data", "IP2LOCATION-COUNTRY-INFORMATION-BASIC.CSV"))
	print(country.get_country_info("US"))


List down region information
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

	import os
	import IP2Location

	# Get region code by country code and region
	region = IP2Location.Region(os.path.join("data", "IP2LOCATION-ISO3166-2.CSV")
	print(region.get_region_code("US", "California"))