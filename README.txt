README.txt for catalog website on AWS server

1. IP address and ssh port for reviewer
IP: 52.35.38.167
ssh port: 2200

2. URL for the web application
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/

3. Software installed
Software installed: apache2, libapache2-mod-wsgi, git
(1) apache config file: /etc/apache2/sites-enabled/default.conf
add one line: WSGIScriptAlias / /var/www/html/myapp.wsgi
(2) in /var/www/html directory create file myapp.wsgi

4. Google oauth credential json file for login/logout
this json file is not included in the repository

5. To login as root, private key file udacity_key.rsa
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEA4XXbtAC1/BGoMZhxJO4aXVkUBUR7seuRI/d2H8sPhy/gmrvt
R8BBvo4PFHMeVe9WMBVSUPSPuFED66va8/YE4HgpsuL8bTcmJP2Ad5XISocVo2ZA
M26mqlPyJk1ldJ92eg5Ul5hw/nnYJ3ri5dw/+TiCPSvEWDbT9w/2Vt3NswW+g48H
OwgKBe9OB3dCHKPPzCvayZhIpDzXLj2eI7ZBXty2b6y5zXDgag/dlI12j+EjDcuu
5cMO0D5kwZvn+YhsrECzzNpmqNm3hBlKu7UJLMcaTU2N9P6yXjqrTdHfhQEGRJtT
sWO0x7y7HuVihpXf7usFIKrrtFVB42MtT3ncDQIDAQABAoIBAQDPe123dhwDn+Av
3ADrom8CztIc0twebRHBjp7XPVDJ8OZ6n00KhcQ675KzGAmnvbyMPWLme1mznmLE
RAAYGKR+SjbdmAQDIghpbB0Ib//FjjD8kUGt0ztvbhde5kTioUkvo/Z3F+OMXGbu
VilurVT2Lem1D4z+PV6tc7QYVsBQ6NKJdMskOgs0CfFH5Ad0s8sWa8DIUiqH5cFz
hUZO/ItVd8/PCJl6gdP9SHRX0Y9ziT67FfzOPI8jinq4dYpBgdHyvu+t/xrmU70J
JldedZ8He62tt1Md9JJIXg0sH1c5sBb+gBQlekFuPItHrScXOpOmDApIchAxVd9W
vW4Cz1GFAoGBAP2TfYWTrTK9ehiYu1BWNqhB9R7Fe+GAtxKNMy21XtAKHyYNIVgk
XkynSeav2gobk+caeOZtqedB0Sp6m7oVLP7ztgH6diyjeNvoZoJjhuVqEqqPS0aZ
Fwisg9riqJkXXxJInOkzsevnJosh8EkAkbra/qG8xcDy0/OQmZvh8oyzAoGBAOOd
kVLSfzDAcgcyNUoZZ39I4oT4jqPjXPrIBUyz22mHfkq2soyQp+xyyghLms2upEQC
e3XNpvVtKsa7y7mTREjlX9n1raa7yS+ZDWZWAuFW8DJKYC8mhn0d8onc7/MN7lqp
CSgPQ3hwVRW3idACLrtpqJDKAfOdsU1ASkRzJ9Q/AoGAddgqeH6F+lO2P2ITgyVd
51onyXIrvUPtULDQPQjSFErv6OYnPehA7sy7+np1EUd5t+hEkYobcL7UrzIl1xfq
Pl4Skt7MNriN/V0G7sfENC/UlvFbIWcaHkzWRk4Z3nPPGhcm3PXKVQCql/Rgz/x0
vWry9UVefeob+FCWIqyh5SMCgYEAvAW4OztpF+ORDkK6ZIiRx0J05DTS160EbKD4
R8E3GXh0qdE7swP3w0mbfLi/mvKN/SQzyj9kkM5qDJqrEpQFT1YzFMBufxIWgjwj
Josce/quFkz8IVbot8gaRyn8CMJUSA3kY3QgXwgkMPlZXTvAUM5aEajdbdmw0ciu
0NZza08CgYB6wgx/aX66uPfHJsZumVHfK6f3PIYu7LFXJCSQ+nVu1DBA1dI2+2yB
2dVsdOrNFwKI4A5O472Nua9eUYSwWEn/UtXA4yOLgTNDqxQHTWgW+/l97gPuPT44
53PfwbluAQ/4NL76ems9XeK5cddoDINsvW1ArW8g1j798WxisYUIBg==
-----END RSA PRIVATE KEY-----



######################
## Folder Structure ##
######################
catalog:
1. database_setup.py: setup database catalogitemwithuser.db and object User, Catalog, Item
2. lotsofitem.py: Populate catalogitemwithuser.db
3. project.py: using Flask framework to define website each endpoint behavior. Access address localhost:8000

templates:
webpage templates for each endpoint to be used in project.py

static:
css file for webpage style.


############################################
## availabe endpoints for catalog website ##
############################################
1. show all catalogs and latest 10 updated items
http://localhost:8000/ or http://localhost:8000/catalogs
2. show all items for one catalog
http://localhost:8000/catalog/<string:catalog_name>/items
3. edit one catalog (user must login)
http://localhost:8000/catalog/<string:catalog_name>/edit
4. delete one catalog (user must loging. If delete one catalog successfully, all items under this catalog will also be deleted)
http://localhost:8000/catalog/<string:catalog_name>/delete
5. create one catalog (user must login)
http://localhost:8000/catalog/new
6. show one particular item
http://localhost:8000/catalog/<string:catalog_name>/<string:item_name>
7. edit one item (user must login)
http://localhost:8000/catalog/<string:catalog_name>/<string:item_name>/edit
8 delete one item (user must login)
http://localhost:8000/catalog/<string:catalog_name>/<string:item_name>/delete
9 create one item (user must login)
http://localhost:8000/catalog/newitem
10 user login
http://localhost:8000/login
11. user logout
http://localhost:8000/disconnect
12. API json endpoint
http://localhost:8000/catalogs?format=json
http://localhost:8000/catalog/<string:catalog_name/items?format=json
http://localhost:8000/catalog/<string:catalog_name>/<string:item_name>?format=json



