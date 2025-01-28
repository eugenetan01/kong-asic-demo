docker run -d \
-e "KONG_ROLE=data_plane" \
-e "KONG_DATABASE=off" \
-e "KONG_WASM=on" \
-e "KONG_VITALS=off" \
-e "KONG_CLUSTER_MTLS=pki" \
-e "KONG_CLUSTER_CONTROL_PLANE=xxx.us.cp0.konghq.com:443" \
-e "KONG_CLUSTER_SERVER_NAME=xxx.us.cp0.konghq.com" \
-e "KONG_CLUSTER_TELEMETRY_ENDPOINT=xxx.us.tp0.konghq.com:443" \
-e "KONG_CLUSTER_TELEMETRY_SERVER_NAME=xxx.us.tp0.konghq.com" \
-e "KONG_CLUSTER_CERT=-----BEGIN CERTIFICATE-----
xxx
-----END CERTIFICATE-----" \
-e "KONG_CLUSTER_CERT_KEY=-----BEGIN PRIVATE KEY-----
xxx
-----END PRIVATE KEY-----" \
-e "KONG_LUA_SSL_TRUSTED_CERTIFICATE=system" \
-e "KONG_KONNECT_MODE=on" \
-e "KONG_CLUSTER_DP_LABELS=created-by:quickstart,type:docker-macOsArmOS" \
-p 8000:8000 \
-p 8443:8443 \
-p 9080:9080 \
kong/kong-gateway:3.9
