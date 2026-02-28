The admin URL is <https://__DOMAIN____PATH__admin>. 

The data directory for the default volume server is located at `/home/yunohost.app/seaweedfs/datadir`.  
Additional data directories can be added via config panel.

:key: Admin credentials for __ADMIN__ :  
`AWS_ACCESS_KEY_ID=__ADMIN_KEY__`   
`AWS_SECRET_ACCESS_KEY=__ADMIN_SECRET__`  

Buckets can be created with `path_style` and `virtual_host`.  
With `virtual_host`:  
* add a domain named `<bucket_name>.__DOMAIN__`
* Install the [Redirect App](https://apps.yunohost.org/app/redirect) (`redirect_ynh`) at the root of this domain and make it point to http:/__PORT_API__
