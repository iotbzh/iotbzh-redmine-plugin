# About

* Easy time tracking plugin
* Allow users to add time directly from calendar view
  * Week view
  * Working week view
  * Month view
  * Month working view

## Installation

* connect to redmine installation

```
cd $REDMINE_DIR/plugins/
git clone https://github.com/iotbzh/iotbzh-redmine-plugin
```

* Enable plugin in Redmine webinterface and restart web server

```
systemctl restart httpd/apache2/nginx
```

* Plugin is available from top banner : EasyTT

## Specific for wiki

* The plugin had a wiki shortcut in topbar.
* If you want to edit or delete the link, edit  **init.rb** file and change 

```
menu :top_menu, :wiki, { :controller => 'wiki', :action =>  'index', :project_id => 'iot-team'  }, :caption => 'WIKI'
```

