# About

* Easy time tracking plugin
* Allow users to add time directly from calendar view
  * Week view
  * Working week view
  * Month view
  * Month working view

## Installation

* Install the plugin in the plugins directory

```console
user@localhost$ cd $REDMINE_DIR/plugins/
user@localhost$ git clone https://github.com/iotbzh/iotbzh-redmine-plugin iotbzh
```
**NOTE:** The plugin directory must be named ```iotbzh```, rename it if you forget to set it on
the git clone command.

* Restart your webserver

```console
user@localhost$ systemctl restart httpd/apache2/nginx
```

* Plugin is available from top banner : EasyTT

## Debugging

To be able to debug Redmine and this plugin to open the Redmine folder, not the plugin's one.
Also, you will need to following:

**Visual Code extensions**:
* [Ruby](https://marketplace.visualstudio.com/items?itemName=rebornix.ruby)
* [Rails](https://marketplace.visualstudio.com/items?itemName=bung87.rails)

**Gems**:
```console
user@localhost$ gem install ruby-debug-ide
user@localhost$ gem install debase
```

**launch.json**:
You need to create a ```.vscode/launch.json``` file:
```json
{
	"configurations": [{
		"name": "Redmine Server",
		"type": "Ruby",
		"request": "launch",
		"program": "${workspaceRoot}/bin/rails",
		"args": [ "server", "webrick", "-e", "production"]
	}]
}
```
Adapt the argument ```production``` to your need. This will launch a ```Redmine``` instance on
[http://localhost:3000](http://localhost:3000).

## Specific for wiki

* The plugin had a wiki shortcut in topbar.
* If you want to edit or delete the link, edit  **init.rb** file and change 

```
menu :top_menu, :wiki, { :controller => 'wiki', :action =>  'index', :project_id => 'iot-team'  }, :caption => 'WIKI'
```

