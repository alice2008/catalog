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
file content is included in the comments.


######################
## Folder Structure ##
######################
catalog:
1. database_setup.py: setup database catalogitemwithuser.db and object User, Catalog, Item
2. lotsofitem.py: Populate catalogitemwithuser.db
3. project.py: using Flask framework to define website each endpoint behavior. Access address ec2-52-35-38-167.us-west-2.compute.amazonaws.com

templates:
webpage templates for each endpoint to be used in project.py

static:
css file for webpage style.


############################################
## availabe endpoints for catalog website ##
############################################
1. show all catalogs and latest 10 updated items
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/ or http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalogs
2. show all items for one catalog
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/items
3. edit one catalog (user must login)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/edit
4. delete one catalog (user must loging. If delete one catalog successfully, all items under this catalog will also be deleted)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/delete
5. create one catalog (user must login)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/new
6. show one particular item
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/<string:item_name>
7. edit one item (user must login)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/<string:item_name>/edit
8 delete one item (user must login)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/<string:item_name>/delete
9 create one item (user must login)
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/newitem
10 user login
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/login
11. user logout
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/disconnect
12. API json endpoint
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalogs?format=json
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name/items?format=json
http://ec2-52-35-38-167.us-west-2.compute.amazonaws.com/catalog/<string:catalog_name>/<string:item_name>?format=json



