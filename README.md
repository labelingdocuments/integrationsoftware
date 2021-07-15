# integration specs

Below the last available specs for integration within G-L-S it systems in Italy, as a mix of SOAP/XML and GET/POST simil-REST API.

**CREATING SHIPMENTS**
* [Labeling API Rev. 17](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU162_Web%20Integrated%20Labeling%20Service_REV17.pdf)

* [Address Validation API Rev. 4](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU163_Webservice_Checkaddress_rev_04.pdf)


**TRACKING SHIPMENTS**
* [Track & Trace API Rev 7](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU40%20-%20Track%20%20Trace%20rev7.pdf)

* [Track & Trace Standard Codes](https://github.com/labelingdocuments/integrationsoftware/blob/master/standard_tracking_codes.xls) for uses with normal delivery

* [Track & Trace Full Codes](https://github.com/labelingdocuments/integrationsoftware/blob/master/codici_risultato_gls.xls) - Full Track and Trace Codes

**FAILED DELIVERY MANAGEMENT**

* [Track & Trace Failed Delivery - Required Actions Codes](https://github.com/labelingdocuments/integrationsoftware/blob/master/tracking_codes_requiring_sender_action.xlsx) whereby it's mandatory for sender to take action

* [Stock Release API](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU276_SvincoloGiacenzeXML_70337bb8-9a58-440a-a7df-eb3270fcac96%20(1).pdf) - For taking actions on Failed Delivery Notes: This does not support Flexdelivery/ECOM custom handling

**RESOURCES FOR ADDRESS VALIDATION AND FIXING**

* [Character Conversion sheets for Labeling API](https://github.com/labelingdocuments/integrationsoftware/blob/master/GLS%20Webservice%20-%20Tabella%20Conversione.xlsx) - You should convert the address characters accordinly to that table. Thanks Mr. Tribuni

* ZIP Code are 5-digits long and for validation and fixing it's possible to use the [Comuni-json](https://github.com/matteocontrini/comuni-json) database
  * ZIP Code in Italy do follow that rules that enable cross-province code validation
   * The 1st digit of zipcode is the Region.
   * The 2nd digit of zipcode is the Province.

* [ZIP Codes in XLS](https://github.com/labelingdocuments/integrationsoftware/blob/master/CAP_ITALIA_2020.xlsx) with Municipality and Region of all Italy, up to date for 2020
 
* [Province name with Province code](https://github.com/labelingdocuments/integrationsoftware/blob/master/province-it.xls) are useful for address preparation and fixing, before labeling.

* [Minor Islands Zip Codes](https://github.com/labelingdocuments/integrationsoftware/blob/master/Isole_Minori_Rev6_Mar21.xlsx) is useful for excluding high-cost destination based on A) ZIP Codes B) CheckAddress() API's results

**POST DELIVERY**

* POD (Proof of Delivery) can be uploaded by G-L-S in Italy automatically to a destination FTP or SFTP server and via email. Note: CAO
  *  POD can be uploaded in JPEG, PDF, TIFF format.
  *  POD file name can be A) NSped (shipment number) B) DDT (Internal shipment identifier in "BDA" field) 

* [Pickup API](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU302_Ritiri_XML_rev2_3d1def7c-da62-4692-b927-c9059c9187b8.pdf) - Handling Pickups for return

**TESTING API**

For testing SOAP interfaces (Labeling and Address Validation):
* [SOAP UI](https://www.soapui.org/tools/soapui/) opensource graphical tool

For testing AddParcel() HTTP POST interfaces, in a simple way using [curl](https://curl.se/):
* curl -X POST -d @Request-Template-AddParcel.xml-POST-TEMPLATE.txt https://labelservice.gls-italy.com/ilswebservice.asmx/AddParcel

For testing Track and Trace API using HTTP GET the following URI:
* Departure: /XML/get_xml_track.php?locpartenza=<WAREHOUSEOFDEPARTURE>&NumSped=<NUMSPED>&CodCli=<CUSTOMERID>
* Pick-up: /XML/get_xml_track.php?locpartenza=<WAREHOUSEOFPICKUP>&numrit=<NUMBEROFPICKUP>&CodCli=>CUSTOMERID>
* Return:  /XML/get_xml_track.php?sedecon=<WAREHOUSEOFDEPARTURE>&CodCli=<CUSTOMERID>&idreso=<IDRESO>   <---- NOTE: IDRESO by default is the NUMSPED of DEPARTURE

                                                                                                             
# integrationsoftware
Collection of existing opensource software that integrate with G-L-S  IT systems (XML, FTP, Web, etc) in Italy

An unofficial PHP SDK for the G-L-S webservice in Italy
https://github.com/markosirec/gls-italy-sdk

Java GLSConnector for Weblabelng
https://github.com/CodeVicious/GLSConnector

Some kind of big multi-courier shipping manager with G-L-S support in Italy
https://github.com/munanshu/zfs

Odoo modules for G-L-S labeling in Italy
https://github.com/it-spiderman/odoo_modules/ -> https://github.com/it-spiderman/odoo_modules/tree/master/gls_label_2
