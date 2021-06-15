# integration specs

Below the last available specs for integration within G-L-S it systems in Italy, as a mix of SOAP/XML and GET/POST simil-REST API.

* [Labeling API Rev. 17](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU162_Web%20Integrated%20Labeling%20Service_REV17.pdf)

* [Address Validation API Rev. 4](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU163_Webservice_Checkaddress_rev_04.pdf)

* [Track & Trace API Rev 7](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU40%20-%20Track%20%20Trace%20rev7.pdf)

* [Stock Release API](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU276_SvincoloGiacenzeXML_70337bb8-9a58-440a-a7df-eb3270fcac96%20(1).pdf) - Notes: This does not support Flexdelivery/ECOM custom handling

* [Pickup API](https://github.com/labelingdocuments/integrationsoftware/blob/master/MU302_Ritiri_XML_rev2_3d1def7c-da62-4692-b927-c9059c9187b8.pdf) - Handling Pickup

* [Character Conversion Requirements sheets for Labeling API](https://github.com/labelingdocuments/integrationsoftware/blob/master/GLS%20Webservice%20-%20Tabella%20Conversione.xlsx) - You should convert the address characters accordinly to that table. Thanks Mr. Tribuni

* [Track & Trace Codes means and actions](https://github.com/labelingdocuments/integrationsoftware/blob/master/codici_risultato_gls.xls) - You should consider the meaning of all the codes accordinly to that table.

* [Minor Islands Zip Codes](https://github.com/labelingdocuments/integrationsoftware/blob/master/Isole_Minori_Rev6_Mar21.xlsx) along with CheckAddress detection methods

* POD (Proof of Delivery) can be uploaded by G-L-S in Italy automatically to a destination FTP or SFTP server and via email. Note: CAO
**  POD can be uploaded in JPEG, PDF, TIFF format.
**  POD file name can be A) NSped (shipment number) B) DDT (Internal shipment identifier in "BDA" field) 

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
