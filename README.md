# fsqueuemon

Web status monitor for FreeSWITCH's mod_callcenter queues and agents

![Screenshot](https://raw.githubusercontent.com/gonicus/fsqueuemon/master/screenshot.png)

## Description

A simple web status monitor / dashboard for mod_callcenter. It will show active/inactive agents and queued callers.

fsqueuemon is implemented in Python using the Flask web microframework (http://flask.pocoo.org/).
It uses FreeSWITCH's `mod_xml_rpc` to interact with FreeSWITCH using XML-RPC.

## Setup

The `queuemon.py` script can be executed to locally start a development server.
See the Flask documentation for deployment options.

Please adapt these three settings to your environment:

* `domain` in `backends.py` should be the domain part of the queues/agents you want to display
* `URI` in `queuemon.py` to access `mod_xml_rpc`
* `hide_agents` can contain agents that should never be shown

## Install

Simple install instructions:

  mkvirtualenv fsqueuemon
  cd /app/
  git clone https://github.com/areski/fsqueuemon.git
  cd fsqueuemon
  pip install -r requirements.txt
  python queuemon.py

Configure:

  cp config.py private_config.py

Then edit `private_config.py` and set your correct XML_RPC settings as well as your domain.

## Deploy

Deploy in production using gunicorn, ref: https://medium.com/@mthipparthi/supervisor-to-control-flask-gunicorn-ec07e81a26b6

## ToDo

The few strings in the UI are German right now and not yet i18nalized.

