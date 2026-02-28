The admin URL is <https://__DOMAIN____PATH__admin>. 

### Credentials

:key: Admin credentials for __ADMIN__ :  
`AWS_ACCESS_KEY_ID=__ADMIN_KEY__`   
`AWS_SECRET_ACCESS_KEY=__ADMIN_SECRET__`  

Additional credentials can be created via the SeaweedFS admin panel.

### Volume servers

The data directory for the default volume server is located at `/home/yunohost.app/seaweedfs/datadir`.  
Additional data directories can be added by creating additional volume servers via the configuration panel.

### Bucket creation
Buckets can be created using either `path_style` or `virtual_host` access.
With `virtual_host`:  
* add a domain named `<bucket_name>.__DOMAIN__`
* Install the [Redirect App](https://apps.yunohost.org/app/redirect) (`redirect_ynh`) at the root of this domain and configure it in `reverse_proxy` mode to point to `http://127.0.0.1:__PORT_API__ `
