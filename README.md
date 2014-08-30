# JupyterHub: A multi-user server for Jupyter notebooks

This repo hosts the development of a multi-user server to manage and proxy multiple instances of the single-user <del>IPython</del> Jupyter notebook server.

Three actors:

- multi-user Hub (tornado process)
- configurable http proxy (node-http-proxy)
- multiple single-user IPython notebook servers (Python/IPython/tornado)

Basic principles:

- Hub spawns proxy
- Proxy forwards ~all requests to hub by default
- Hub handles login, and spawns single-user servers on demand
- Hub configures proxy to forward url prefixes to single-user servers

## dependencies
    
    # get the nodejs proxy (-g for global install)
    npm install [-g] jupyter/configurable-http-proxy
    
    # install the Python pargs (-e for editable/development install)
    pip install [-e] .

## to use

    $> jupyterhub

visit `http://localhost:8000`, and login with your unix credentials.

