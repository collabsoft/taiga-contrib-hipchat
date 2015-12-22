Taiga contrib HipChat
=====================

The Taiga plugin for HipChat integration.

Installation
------------

#### Taiga Back

In your Taiga back python virtualenv install the pip package taiga-contrib-hipchat with:

```bash
  pip install taiga-contrib-hipchat
```

Modify your settings/local.py and include the line:

```python
  INSTALLED_APPS += ["taiga_contrib_hipchat"]
```

Then run the migrations to generate the new need table:

```bash
  python manage.py migrate taiga_contrib_hipchat
```

### Taiga Front

Download in your `dist/plugins/` directory of Taiga front the `taiga-contrib-hipchat` compiled code (you need subversion in your system):

```bash
  cd dist/
  mkdir -p plugins
  cd plugins
  svn export "https://github.com/taigaio/taiga-contrib-hipchat/tags/$(pip show taiga-contrib-hipchat | awk '/^Version: /{print $2}')/front/dist" "hipchat"
```

Include in your dist/conf.json in the contribPlugins list the value `"/plugins/hipchat/hipchat.json"`:

```json
...
    "contribPlugins": [
        (...)
        "/plugins/hipchat/hipchat.json"
    ]
...
```

How to use
----------

Follow the instructions on our support page [Taiga.io Support > Contrib Plugins > HipChat integration](https://taiga.io/support/hipchat-integration/ "Taiga.io Support > Contrib Plugins > HipChat integration")
