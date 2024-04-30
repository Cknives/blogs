# jq 多个过滤器表达
jq 'select(.verb=="create" and .responseStatus.code==201) |select (.userAgent|contains("oauth-apiserver"))'  /var/log/kube-apiserver/audit.log

# jq 单个多滤器表达，-c紧凑输出
jq -c 'select(.verb=="create" and .responseStatus.code==201 and (.userAgent|contains("oauth-apiserver")))'  /var/log/kube-apiserver/audit.log
