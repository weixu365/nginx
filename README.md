# nginx
An official read-only mirror of http://hg.nginx.org/nginx/ which is updated hourly. Pull requests on GitHub cannot be accepted and will be automatically closed. The proper way to submit changes to nginx is via the nginx development mailing list, see http://nginx.org/en/docs/contributing_changes.html

Added http upstream keepalive timeout settings

Example config

```
upstream nodejs {
  least_conn;
  server chalice:8000 fail_timeout=1s max_fails=3;
  server chalice:8001 fail_timeout=1s max_fails=3;
  keepalive 16 timeout=10s;
}
```
