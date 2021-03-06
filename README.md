# splunk-dash-nginx

## access.log format

Configure nginx to have the access.log format as follows:

```
log_format new  'time_local="$time_local" protocol="$server_protocol" status="$status" '
                    'site="$server_name" server="$host" dest_port="$server_port" dest_ip="$server_addr" '
                    'src="$remote_addr" user="$remote_user" '
                    'bytes_out="$body_bytes_sent" bytes_in="$upstream_response_length" '
                    'http_referer="$http_referer" http_user_agent="$http_user_agent" '
                    'nginx_version="$nginx_version" http_x_forwarded_for="$http_x_forwarded_for" '
                    'http_x_header="$http_x_header" uri_query="$query_string" uri_path="$uri" '
                    'http_method="$request_method" response_time="$upstream_response_time" '
                    'cookie="$http_cookie" request_time="$request_time" ';

    access_log  /var/log/nginx/access.log  new;
```

## splunk dashboard setup

1. At splunk create a new dashboard
2. Give title of Nginx, create
3. Click source tab 
4. Paste  in the contents of splunk source nginx.xml

